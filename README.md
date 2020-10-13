# Sapling 
- current release: `v0.1` [released for alpha testing]
- Aims to help students pin-point answers *(1)* from a large corpus of journal articles. It could also work for other formats of texts, suchs as textbook chapters or e-books.
- In doing so, the creation of Sapling hopes :-
	1. to reduce the time needed by students' to learn about a (usually new) topic 
	2. to provides answers on the fly, such as during lectures and in workgroup sessions, or when refreshing knowledge on topics that was learnt months or years ago
	3. to help reduce anxiety (due to information overload) while preparing for exams or essay writing
	4. to ultimately reduce the knowledge acquisition barrier to help every one succeed in their education journey
- Inspired by advancements in AI on Natural Language Processing (NLP) such as IBM's Watson, FB's DrQA, and Google Research's BERT & ALBERT.


## Features
1. **Finds the 5 most relevant sentences across multiple PDF articles within minutes** to answer your question about any topic. Confidence scores of each result are displayed!
2. Is also able to locate the files and paragraphs the answers are in. You can open the file from the results if you want to.
3. Leverages modern computing capability and speed to **quickly 'read' contents among texts**. `Sapling` works best when more texts files are being fed *(2)*. You could for example feed it with all the articles and book chapters required for a course!
4. Currently **supports most `PDFs` files**. Support for `.txt` and `docx` will be added in an upcoming version.
5. Uses *nearly* state-of-the-art human language comprehension and question answering architechture (produced in end-2019 to early-2020)


## Getting Started:
1. **Setup Sapling for the first time**	
	- Download 'Sapling' for 
		1. [Windows (175MB)](https://drive.google.com/file/d/14239sQrEaYe1HultlYYcJNlNxUEZ82VC/view?usp=sharing) 
		2. [Mac (400MB)]()

	- Download and install latest Java runtime 
		- Download for [any platform (recommended)](https://java.com/en/download/) 
		- OR for [specific platform (advanced)](https://java.com/en/download/manual.jsp)

2. **Extract and run**
	- *Windows*
		1. Run `autorun.bat` after extracting the zip file
		2. You could also create shortcut for the `.bat` to desktop
	- *Mac*
		1. Run `autorun.sh` 

3. **Provide path to the folder with your PDFs**
	- This is the knowledge base which Sapling draw her answers from
	- *MacOS*: **Copy the path of the directory that you want to load**
		1. ***Option 1:***
			- Drag and drop into the console window
		2. ***Option 2:***
			- Right click on the folder, then **hold** the 'option' button. You should see 'Copy `your folder` as pathname' option
			- [ ] to add screenshots		
	- Windows users can also drag and drop into the console

4. **Question away!**
	- Ask anything you like or something you vaguely remember from reading the texts


## FAQ
1. What it means by `texts are not parsable`?
2. Why am I getting `failed to see startup message` error?

## Technical description
- WIP

### Version Releases
- v0.1 [13-Oct-2020]: debut for alpha testing
	- *features available*
		1. Extract clean texts from PDFs
		2. Return 5 top matching sentences to your query

#### *Notes*
1. Sapling's internal model was trained to understand public domain language and has not been trained on domain specific language, such as Political Science or Arts. That may reduce accuracy of answers slightly, but this limitation will be improved in future releases based on user feedbacks.
2. Sapling has not yet been tested to its limit, but will perform slower when given hundreds of files. Performance is also machine dependant: processor speed, memory size and availability of Cuda-GPUs.

#### Ideas for the future:
- *Features*
	- [ ] ability to change the number of results returned
	- [ ] improve search speed
	- [ ] tidier preprocessing of PDF headers, footers and citations
	- [ ] web-based UI
	- [ ] OCR capability for unparsable PDFs
	- [ ] extract text from docx files
	- [ ] save outputs

- *Bug fixes*
	- [ ] None