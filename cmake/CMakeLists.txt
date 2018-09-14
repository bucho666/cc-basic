# バージョン指定
cmake_minimum_required(VERSION 3.1)
# プロジェクト名
project(helloworld CXX)
# Cのバージョン指定
set(CMAKE_CXX_STANDARD 11)
# コンパイルオプション
set(CMAKE_CXX_FLAGS "-O2 -Wall")
# サブモジュール定義
set(submodules hello world)
# カレントディレクトリのソースファイル取得
file(GLOB sorces *.cc)
# 実行ファイルと依存ファイル
add_executable(${PROJECT_NAME} ${sorces})
# サブディレクトリ追加
foreach(dir ${submodules})
  add_subdirectory(${dir})
endforeach()
# ヘッダファイルパス追加
target_include_directories(${PROJECT_NAME} PUBLIC ${submodules})
# リンクライブラリ設定
target_link_libraries(${PROJECT_NAME} ${submodules})
