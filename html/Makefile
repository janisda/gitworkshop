default: html
html:
	for f in ../*; do \
		if [ ! -d $$f ]; then \
			(cat .generate/header.html; \
				.generate/Markdown.pl $$f;\
				echo '</body></html>') \
			> `basename $$f`.html; \
		fi; \
	done
clean:
	rm -f *.html
