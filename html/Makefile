default: html
html:
	for d in $$(find ../md/ -type d) ; do \
		mkdir -pv $${d#../md/} ; \
	done

	for f in $$(find ../md/ -type f -not -name "*~"); do \
		echo -n generating $${f#../md/}.html... ; \
		(cat .generate/header.html; \
			.generate/Markdown.pl $$f;\
			echo '</body></html>') \
		> $${f#../md/}.html; echo done.; \
	done
clean:
	rm -f *.html
