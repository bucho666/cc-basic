# バージョン指定
cmake_minimum_required(VERSION 2.8)
# プロジェクト名
project(world)
# カレントディレクトリのソースファイル取得
file(GLOB sorces *.cc)
# ライブラリファイルと依存ファイル
add_library(${PROJECT_NAME} SHARED ${sorces})
