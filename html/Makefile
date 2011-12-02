default: html
html:
	for f in $$(find ../md/ -type f -not -name "*~"); do \
		if [ ! -d $$f ]; then \
			echo -n generating $${f#../md/}.html... ; \
			(cat .generate/header.html; \
				.generate/Markdown.pl $$f;\
				echo '</body></html>') \
			> $${f#../md/}.html; echo done.; \
		else \
			mkdir -vp $${f#../md/}; \
		fi; \
	done
clean:
	rm -f *.html
