default: html
html:
	for d in $$(find ../md/ -type d -not -path ../md/) ; do \
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
	find . -name "*.html" -not -path ./.generate/header.html | xargs rm -f
	for d in $$(find ../md/ -type d -not -path ../md/) ; do \
		rmdir -pv $${d#../md/} ; \
	done
