set( LLVM_LINK_COMPONENTS
  ${LLVM_TARGETS_TO_BUILD}
  Option
  Support
  )

add_clang_executable(clang-astparser
  clang-astparser.cpp
  )

clang_target_link_libraries(clang-astparser
  PRIVATE
  clangAST
  clangBasic
  clangFrontend
  clangRewrite
  clangTooling
  clangAnalysis
  )

install(TARGETS clang-astparser
  RUNTIME DESTINATION bin)
