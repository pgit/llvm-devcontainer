FROM clang-centos7:latest

RUN yum install -y devtoolset-10 && yum clean all
RUN yum install -y libatomic && yum clean all

RUN echo >>~/.bashrc && \
    echo >>~/.bashrc 'source scl_source enable devtoolset-10' && \
    echo >>~/.bashrc 'source scl_source enable rh-python36'

RUN echo >>~/.bash_history '(cd build && ninja clangd) && build/bin/llvm-lit clang-tools-extra/clangd/test --filter pragma-visibility -a'
