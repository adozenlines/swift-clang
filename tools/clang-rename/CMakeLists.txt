set(LLVM_LINK_COMPONENTS
  Option
  Support
  )

add_clang_tool(clang-rename ClangRename.cpp)

target_link_libraries(clang-rename
  PRIVATE
  clangBasic
  clangFrontend
  clangRewrite
  clangTooling
  clangToolingCore
  clangToolingRefactor
  clangToolingRefactoring
  )

install(PROGRAMS clang-rename.py
  DESTINATION share/clang
  COMPONENT clang-rename)
install(PROGRAMS clang-rename.el
  DESTINATION share/clang
  COMPONENT clang-rename)
