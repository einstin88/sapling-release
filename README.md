# Sapling 
- current release: `v0.1` [released for alpha testing]
- Aims to help students pin-point answers*(1)* from a large corpus of journal articles. It could also work for other formats of texts, suchs as textbook chapters or e-books.
- In doing so, the creation of Sapling hopes :-
	1. to reduce the time needed by students' to learn about a (usually new) topic 
	2. to provides answers on the fly, such as during lectures and in workgroup sessions, or when refreshing knowledge on topics that was learnt months or years ago
	3. to help reduce anxiety (due to information overload) while preparing for exams or essay writing
	4. to ultimately reduce the knowledge acquisition barrier to help every one succeed in their education journey
- Inspired by advancements in AI on Natural Language Processing (NLP) such as IBM's Watson, FB's DrQA, and Google Research's BERT & ALBERT.


## Features
- Finds the 5 most relevant sentences across multiple PDF articles within minutes to answer your question about a topic. Confidence scores of each result are displayed!
- Is also able to locate the files and paragraphs the answers are in. You can open the file from the results if you want to.
- Leverages modern computing capability and speed to **quickly 'read' contents among texts**. `Sapling` works best when more texts files are being fed *(2)*. You could for example feed it with all the articles and book chapters required for a course!
- Currently **supports most `PDFs` files**. Support for `.txt` and `docx` will be added in an upcoming version.
- Uses *nearly* state-of-the-art human language comprehension and question answering architechture (produced in end-2019 to early-2020)


## Getting Started:
1. **Setup Sapling for the first time**	
	- Download 'Sapling' for 
		1. [Windows (175MB)](https://drive.google.com/file/d/14239sQrEaYe1HultlYYcJNlNxUEZ82VC/view?usp=sharing) 
		2. [Mac (400MB)]()

	- latest Java runtime installed 
		- Download for [any platform (recommended)](https://java.com/en/download/) OR [specific platform (advanced)](https://java.com/en/download/manual.jsp)

2. (*MacOS*) **Copy the path of the directory that you want to load**
	- ***Option 1:***
		- [ ] to add descriptions and screenshots

	- ***Option 2:***

3. **Run**
4. **Provide folder with your files**
5. **Question away!**


## FAQ
1. What it means by texts are not parsable?
2. Why am I getting `failed to see startup message` error?

## Technical description
- WIP

### Version Releases
- v0.1 [end-Sep-2020] - alpha testing + initial release
	- *features available*
		1. Extract texts from PDFs
		2. Return 5 top matching sentences to your query

### *Notes*
1. Sapling's internal model was trained to understand public domain language and has not been trained on domain specific language, such as Political Science or Arts. That may reduce accuracy of answers slightly, but this limitation will be improved in future releases based on user feedbacks.
2. Sapling has not yet been tested to its limit, but will perform slower when given hundreds of files. Performance is also machine dependant: processor speed, memory size and availability of Cuda-GPUs.

### Ideas for the future:
- *Features*
	- [ ] ability to change the number of results returned
	- [ ] tidier preprocessing of PDF headers, footers and citations
	- [ ] web-based UI
	- [ ] OCR capability for unparsable PDFs
	- [ ] extract text from docx files
	- [ ] save outputs

- *Bug fixes*
	- [ ] None