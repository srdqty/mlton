## Copyright (C) 2009 Matthew Fluet.
 # Copyright (C) 1999-2006 Henry Cejtin, Matthew Fluet, Suresh
 #    Jagannathan, and Stephen Weeks.
 # Copyright (C) 1997-2000 NEC Research Institute.
 #
 # MLton is released under a BSD-style license.
 # See the file MLton-LICENSE for details.
 ##

SRC := $(shell cd .. && pwd)
BUILD := $(SRC)/build
BIN := $(BUILD)/bin
LIB := $(BUILD)/lib/mlton
MLTON := mlton
TARGET := self
FLAGS := -target $(TARGET) -default-ann 'sequenceNonUnit warn' -default-ann 'warnUnused true'
NAME := mlprof
PATH := $(BIN):$(shell echo $$PATH)

all:	$(NAME)

$(NAME): $(NAME).mlb $(shell PATH="$(BIN):$$PATH" && "$(MLTON)" -stop f $(NAME).mlb)
	@echo 'Compiling $(NAME)'
	$(MLTON) $(FLAGS) $(NAME).mlb

.PHONY: clean
clean:
	../bin/clean

.PHONY: test
test: $(NAME)
	./mlprof z mlmon.out
