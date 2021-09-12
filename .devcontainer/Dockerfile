FROM psedoc/centos7-devtools:latest

RUN yum install -y libatomic && yum clean all

RUN echo >>~/.bashrc && \
    echo >>~/.bashrc 'source scl_source enable devtoolset-10' && \
    echo >>~/.bashrc 'source scl_source enable rh-python36'
RUN echo >>~/.bashrc 'cd llvm-project'

RUN echo >>~/.bash_history '(cd ../build && ninja clangd) && build/bin/llvm-lit clang-tools-extra/clangd/test --filter pragma-visibility -a'
