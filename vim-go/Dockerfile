FROM golang:1.10-alpine3.7

RUN apk --no-cache --upgrade add \
    ctags \
    curl \
    git \
    vim

RUN go get \
    github.com/direnv/direnv \
    github.com/jstemmer/gotags \
    golang.org/x/tools/cmd/godoc \
    golang.org/x/tools/cmd/goimports \
    golang.org/x/lint/golint \
    golang.org/x/tools/cmd/guru

RUN mkdir -p ~/.vim/autoload ~/.vim/bundle && \
    curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

ARG VIM_GO_TAG=v1.17
RUN mkdir -p ~/.vim/bundle && \
    git clone -q https://github.com/fatih/vim-go.git ~/.vim/bundle/vim-go --branch $VIM_GO_TAG

ARG NERDTREE_TAG=5.0.0
RUN mkdir -p ~/.vim/bundle && \
    git clone -q https://github.com/scrooloose/nerdtree.git ~/.vim/bundle/nerdtree --branch $NERDTREE_TAG

ARG TAGBAR_TAG=v2.7
RUN mkdir -p ~/.vim/bundle && \
    git clone -q https://github.com/majutsushi/tagbar.git ~/.vim/bundle/tagbar --branch $TAGBAR_TAG

ARG CTRLP_TAG=1.80
RUN mkdir -p ~/.vim/bundle && \
    git clone -q https://github.com/ctrlpvim/ctrlp.vim.git ~/.vim/bundle/ctrlp --branch $CTRLP_TAG

COPY vimrc /root/.vimrc
