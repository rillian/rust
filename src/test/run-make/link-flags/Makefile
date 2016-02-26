-include ../tools.mk
all: foo
	
foo: foo.rs $(call STATICLIB,bar)
	$(RUSTC) $<
	$(call RUN,$@)

$(call STATICLIB,bar) bar.ldflags : bar.rs
	$(RUSTC) $^ --crate-type staticlib --crate-name bar \
	  --emit link,link-flags-ld=bar.ldflags
