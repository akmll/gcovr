all:
	cd 'src code'; $(CXX) -fprofile-arcs -ftest-coverage -fPIC main.cpp -o testcase

run: txt xml html sonarqube

txt:
	cd 'src code'; ./testcase
	$(GCOVR) -r 'src code' -d -o coverage.txt

xml:
	cd 'src code'; ./testcase
	$(GCOVR) -r 'src code' -d -x -o coverage.xml

html:
	cd 'src code'; ./testcase
	$(GCOVR) -r 'src code' -d --html-details -o coverage.html

sonarqube:
	cd 'src code'; ./testcase
	$(GCOVR) -r 'src code' -d --sonarqube sonarqube.xml

clean:
	rm -f */testcase
	rm -f */*.gc*
	rm -f coverage.txt coverage.xml coverage*.html sonarqube.xml
