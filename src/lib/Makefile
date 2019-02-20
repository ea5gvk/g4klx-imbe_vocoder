CXX    := g++
CFLAGS := -O2 -Wall

OBJECTS = aux_sub.o ch_encode.o dsp_sub.o imbe_vocoder_impl.o pitch_est.o rand_gen.o sa_enh.o v_synt.o \
          basicop2.o dc_rmv.o encode.o math_sub.o pitch_ref.o sa_decode.o tbls.o v_uv_det.o ch_decode.o \
          decode.o imbe_vocoder.o pe_lpf.o qnt_sub.o sa_encode.o uv_synt.o

.PHONY: all
all:		imbe.a

imbe.a:	$(OBJECTS)
		$(AR) rcs imbe.a $(OBJECTS)

-include $(OBJECTS:.o=.d)

%.o: %.cc
		$(CXX) $(CFLAGS) -c -o $@ $<
		$(CXX) -MM $(CFLAGS) $< > $*.d

.PHONY: clean
clean:
		$(RM) imbe.a *.o *.d *.bak *~

