# Copyright (C) 2008, 2009,2012 Her Majesty the Queen in Right of Canada
# (Communications Research Center Canada)
# Pascal Charest
#
# Copyright (C) 2014, Matthias P. Braendli, http://mpb.li
#

# This file is part of ODR-DabMux.
# 
# ODR-DabMux is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as
# published by the Free Software Foundation, either version 3 of the
# License, or (at your option) any later version.
# 
# ODR-DabMux is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with ODR-DabMux.  If not, see <http://www.gnu.org/licenses/>.

if IS_GIT_REPO
GITVERSION_FLAGS = -DGITVERSION="\"`git describe`\""
else
GITVERSION_FLAGS =
endif

FEC_FLAGS   =
FEC_LIBS    =-lfec

if HAVE_ZEROMQ_TEST
bin_PROGRAMS=odr-dabmux odr-bridgetest zmqinput-keygen

ZMQ_LIBS    =-lzmq
else
bin_PROGRAMS=odr-dabmux odr-bridgetest

ZMQ_LIBS    =
endif

odr_dabmux_CPPFLAGS =-Wall -I$(FARSYNC_DIR) $(GITVERSION_FLAGS)
odr_dabmux_LDADD    =$(FEC_LIBS) $(ZMQ_LIBS) -lpthread -lboost_thread -lboost_system
odr_dabmux_SOURCES  =DabMux.cpp DabMux.h \
                     dabInput.h dabInput.cpp \
                     dabInputBridgeUdp.h dabInputBridgeUdp.cpp \
                     dabInputDabplusFifo.h dabInputDabplusFifo.cpp \
                     dabInputDabplusFile.h dabInputDabplusFile.cpp \
                     dabInputDmbFile.h dabInputDmbFile.cpp \
                     dabInputDmbUdp.h dabInputDmbUdp.cpp \
                     dabInputEnhancedFifo.h dabInputEnhancedFifo.cpp \
                     dabInputEnhancedPacketFile.h dabInputEnhancedPacketFile.cpp \
                     dabInputFifo.h dabInputFifo.cpp \
                     dabInputFile.h dabInputFile.cpp \
                     dabInputMpegFifo.h dabInputMpegFifo.cpp \
                     dabInputMpegFile.h dabInputMpegFile.cpp \
                     dabInputPacketFile.h dabInputPacketFile.cpp \
                     dabInputPrbs.h dabInputPrbs.cpp \
                     dabInputRawFile.h dabInputRawFile.cpp \
                     dabInputRawFifo.h dabInputRawFifo.cpp \
                     dabInputSlip.h dabInputSlip.cpp \
                     dabInputTest.h dabInputTest.cpp \
                     dabInputUdp.h dabInputUdp.cpp \
                     dabInputZmq.h dabInputZmq.cpp \
                     dabOutput/dabOutput.h \
                     dabOutput/dabOutputFile.cpp \
                     dabOutput/dabOutputFifo.cpp \
                     dabOutput/dabOutputRaw.cpp \
                     dabOutput/dabOutputSimul.cpp \
                     dabOutput/dabOutputTcp.cpp \
                     dabOutput/dabOutputUdp.cpp \
                     dabOutput/dabOutputZMQ.cpp \
                     dabOutput/edi/AFPacket.cpp dabOutput/edi/AFPacket.h \
                     dabOutput/edi/TagItems.cpp dabOutput/edi/TagItems.h \
                     dabOutput/edi/TagPacket.cpp dabOutput/edi/TagPacket.h \
                     dabOutput/edi/PFT.cpp dabOutput/edi/PFT.h \
                     bridge.h bridge.c \
                     utils.cpp utils.h \
                     MuxElements.cpp MuxElements.h \
                     RemoteControl.cpp RemoteControl.h \
                     ParserCmdline.cpp ParserCmdline.h \
                     ParserConfigfile.cpp ParserConfigfile.h \
                     Eti.h Eti.cpp \
                     Log.h Log.cpp \
                     UdpSocket.h UdpSocket.cpp \
                     InetAddress.h InetAddress.cpp \
                     prbs.h prbs.c \
                     crc.h crc.c \
                     dabUtils.h dabUtils.cpp \
                     PcDebug.h \
                     Dmb.h Dmb.cpp \
                     Interleaver.h Interleaver.cpp \
                     ReedSolomon.h ReedSolomon.cpp \
                     mpeg.h mpeg.c \
                     StatsServer.h StatsServer.cpp \
                     TcpServer.h TcpServer.cpp \
                     TcpSocket.h TcpSocket.cpp \
                     zmq.hpp

odr_bridgetest_CFLAGS   =-DBRIDGE_TEST
odr_bridgetest_SOURCES  =bridge.c \
                         crc.c crc.h

zmqinput_keygen_SOURCES  = zmqinput-keygen.c
zmqinput_keygen_LDADD    = $(ZMQ_LIBS)
zmqinput_keygen_CFLAGS   = -Wall $(GITVERSION_FLAGS)

