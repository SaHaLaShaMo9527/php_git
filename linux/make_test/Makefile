#source file
# Դ�ļ����Զ������� .c �� .cpp �ļ�������Ŀ�궨��Ϊͬ�� .o �ļ�
SOURCE  := $(wildcard *.c) $(wildcard *.cpp) \
		   $(wildcard ./source/*.c) $(wildcard ./source/*.cpp)
OBJS    := $(patsubst %.c,%.o,$(patsubst %.cpp,%.o,$(SOURCE)))

#target you can change test to what you want
# Ŀ���ļ�����������������Ҫ��ִ���ļ���
TARGET  := main

COMPILE = gcc 

LIBS    := -L./lib -lm
LIBS    += -lpthread
LDFLAGS:= 
INCLUDE:= -I ./include   

CFLAGS  := -g -Wall -O2 -Wl,-gc-sections $(INCLUDE) 
CFLAGS  += "-fno-strict-aliasing"

CXXFLAGS := $(CFLAGS)
#i think you should do anything here
# ����Ļ����ϲ���Ҫ���κθĶ���
.PHONY : everything objs clean veryclean rebuild prepare

everything : $(TARGET)

all : $(TARGET)

objs : $(OBJS)

rebuild: veryclean everything

clean :
	-rm -f $(OBJS) $(TARGET)

veryclean : clean
	rm -fr $(TARGET)
	
$(TARGET) : prepare $(OBJS) 
	$(COMPILE) $(CXXFLAGS) -o $@ $(OBJS) $(LDFLAGS) $(LIBS)
