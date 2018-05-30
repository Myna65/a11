PROJECT(master_project NONE)
cmake_minimum_required(VERSION 2.8)
SET(LATEX_OUTPUT_PATH build)
INCLUDE(deps/UseLATEX/UseLATEX.cmake)

file(GLOB_RECURSE contents_files RELATIVE ${CMAKE_SOURCE_DIR} include/*.tex)

add_latex_document(full.tex
  BIBFILES references.bib
  INPUTS ${contents_files}
  USE_INDEX
)

add_latex_document(presentation.tex)
