cmake_minimum_required(VERSION 3.15)
project(Chapter3cpp)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)
include_directories(wci)
include_directories(wci/backend)
include_directories(wci/backend/compiler)
include_directories(wci/backend/interpreter)
include_directories(wci/frontend)
include_directories(wci/frontend/pascal)
include_directories(wci/frontend/pascal/tokens)
include_directories(wci/intermediate)
include_directories(wci/message)
find_package(Boost)
IF (Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIR})
endif()


add_executable(Chapter3cpp
        wci/backend/compiler/CodeGenerator.cpp
        wci/backend/compiler/CodeGenerator.h
        wci/backend/interpreter/Executor.cpp
        wci/backend/interpreter/Executor.h
        wci/backend/Backend.cpp
        wci/backend/Backend.h
        wci/backend/BackendFactory.h
        wci/frontend/pascal/tokens/PascalErrorToken.h
        wci/frontend/pascal/tokens/PascalNumberToken.cpp
        wci/frontend/pascal/tokens/PascalNumberToken.h
        wci/frontend/pascal/tokens/PascalSpecialSymbolToken.cpp
        wci/frontend/pascal/tokens/PascalSpecialSymbolToken.h
        wci/frontend/pascal/tokens/PascalStringToken.cpp
        wci/frontend/pascal/tokens/PascalStringToken.h
        wci/frontend/pascal/tokens/PascalWordToken.cpp
        wci/frontend/pascal/tokens/PascalWordToken.h
        wci/frontend/pascal/PascalError.cpp
        wci/frontend/pascal/PascalError.h
        wci/frontend/pascal/PascalErrorHandler.cpp
        wci/frontend/pascal/PascalErrorHandler.h
        wci/frontend/pascal/PascalParserTD.cpp
        wci/frontend/pascal/PascalParserTD.h
        wci/frontend/pascal/PascalScanner.cpp
        wci/frontend/pascal/PascalScanner.h
        wci/frontend/pascal/PascalToken.cpp
        wci/frontend/pascal/PascalToken.h
        wci/frontend/FrontendFactory.h
        wci/frontend/Parser.cpp
        wci/frontend/Parser.h
        wci/frontend/Scanner.h
        wci/frontend/Source.cpp
        wci/frontend/Source.h
        wci/frontend/Token.h
        wci/intermediate/ICode.h
        wci/intermediate/SymTab.h
        wci/message/Message.h
        wci/message/MessageHandler.cpp
        wci/message/MessageHandler.h
        wci/message/MessageListener.h
        wci/message/MessageProducer.h
        wci/Globals.cpp
        wci/Object.h
        depends.hidden
        hello.pas
        hilbert.pas
        makefile
        Pascal.cpp
        Pascal.h
        README
        scannertest.txt
        wolfisland.pas)
