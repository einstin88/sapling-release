![Sapling Logo](https://github.com/einstin88/sapling-release/blob/master/img/original.jpeg)

# Sapling 🌱
- current release: `v0.1` 
- Aims to help students pin-point answers *([1](#note1))* from a large corpus of journal articles. It could also work for other formats of texts, suchs as textbook chapters or e-books.

## Contents
1. [What it does?](#first)
2. [Why Sapling?](#second)
3. [Features](#third)
4. [Getting started](#forth)
5. [FAQ](#fifth)
6. [Technical description](#sixth)

## What it does? (will be refined later) <a name="first"></a>
- **What it does in short**: It reads in the passages of the documents in your folder and determine their relevancy to your questions - imagine a custom Google-like search engine for specific ideas or concepts in your readings! You can then ask Sapling to open the correct document for you and dive right in~~
- You may also use it to do a **negative query**, that is searching the documents to be certain that they don't have the information you are looking for. Useful for filtering! For example, if the retrieved answers turn out to have low confidence scores, it is likely that the information you need is not in those given documents (even after you try rephrasing the question)
- It **does NOT assess** your texts qualitatively, i.e., strengths & weaknesses or arguments, robustness of results or the underlying research methodologies unless they are explicitly mentioned! These tasks will remain the responsibility of the students fortunately/unfortunately 😪


## Why Sapling? <a name="second"></a>
The creation of Sapling hopes :-
1. to reduce the time ⏲ needed by students to learn about any text-based (usually new) topic 
2. to provides answers on the fly, such as during lectures 🙋‍♀️🙋‍♂️ and in workgroup sessions, or when refreshing knowledge on topics that was learnt months or years ago
3. to help reduce anxiety (due to information overload) while preparing for exams 👨‍💻👩‍💻 or essay writing
4. to ultimately reduce the knowledge acquisition barrier to help every one succeed in their education journey
(Inspired by advancements in AI 🤖 on Natural Language Processing (NLP) such as IBM's Watson, FB's DrQA, and Google Research's BERT & ALBERT)


## Features <a name="third"></a>
1. Uses *nearly* state-of-the-art human language comprehension and question answering architechture (produced in end-2019 to early-2020) that does not rely on memorizing words or questions to find answers. (The method is too technical to explain here, look at the article "Attention is all you need" by Google if you are interested )
2. Sapling **reads your texts to find the 5 most relevant sentences across multiple PDF articles within minutes** based on your question about its topic. 😎 Confidence scores of each result are displayed! 
3. Locate the files and paragraphs where the answers are. You can open the file from the results if you want to.
4. Leverages modern computing capability and speed to **quickly 'read' contents among texts**. `Sapling` works best when more texts files are being fed *([2](#note2))*. You could for example feed it with all the articles and book chapters required for a course!
5. Currently **supports most `PDFs` files**. Support for `.txt` and `docx` will be added in an upcoming version. 
6. Works on Windows 10 🍑 and MacOS 13 🍎 or newer.


## Getting Started: <a name="forth"></a>
1. **Setting up**	
	- Download 'Sapling':
		1. [GoogleDrive - Windows (170MB)](https://drive.google.com/file/d/1jNh1BU15eKFKZtZvSNWfRTLj5t7Qx7lz/view?usp=sharing)
		2. [GoogleDrive - MacOS 10.13.6 or newer (200MB)](https://drive.google.com/drive/folders/1-D2qTUL0S43HrnTgIvMqcLLpi6w0mNN9?usp=sharing)

	- Download and install latest **Java** runtime
		- [For Windows](https://java.com/en/download/) 
		- [For MacOS](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) ➡ choose 'macOS installer'

2. **Extract and run**
	- *Windows* : Run `autorun.bat` after extracting the zip file
	- *Mac*: 
		1. Follow instructions in the zipped file to run `autorun.command`.
		2. When you get a prompt about security, goto 'Setting' > 'Security & Privacy' > select 'open anyway'

3. **Provide path to the folder with your PDFs**
	- This is the knowledge base which Sapling draw her answers from.

	- Example: 
		1. this is the folder with the PDFs

	![directory](https://github.com/einstin88/sapling-release/blob/master/img/mac_folder_1.png)
		2. The full path to the folder provided like this

	![then path to the folder](https://github.com/einstin88/sapling-release/blob/master/img/provide_path.png)

	- *MacOS*: **2 easy ways to copy the folder path**
		1. ***Option 1:***
			- Drag and drop into the console window
		2. ***Option 2:***
			- Right click on the folder, then **hold** the 'option' button. You should see 'Copy xxx as pathname' option
	
	![copy path on mac](https://github.com/einstin88/sapling-release/blob/master/img/mac_folder_3.JPG)

	- You can easily drag and drop into the console on Windows

4. **Question away!**
	- Ask anything you like or something you vaguely remember from reading the texts
	- And repeat!
	- Example query & results:

![Example query](https://github.com/einstin88/sapling-release/blob/master/img/query.png)
	
![Results](https://github.com/einstin88/sapling-release/blob/master/img/result_disp.png)


## FAQ <a name="fifth"></a>
1. What it means by `texts are not parsable`?
	- It means that the PDF is a scanned image, or the internal character mapping is corrupt. Usually occur with very old PDFs.

2. Why am I getting `failed to see startup message` error?
	- It takes a couple of seconds to load the PDF parser. Sometimes the first timer is up before it is loaded. If it continues, then don't worry about the message. Otherwise, you may be running with MacOS 10.14 or older, which has old Java setup and will cause strange behaviour.

3. Why am I getting segmentation fault : 11?
	- This should be fixed now. If you're using MacOS, it is due to the way Python and Mac handles memory. You may have feed it with a large file, increasing RAM and cache usage by the program. I will try to fix this in the next version.

4. Why does it take a couple of minutes every time I enter a question?
	- It is still in the preliminary development phase of the program. So the focus is on accuracy of the results. Speed will be improved in the future for sure! Please let us know if you find the program useful or what needs to be improved, so it can be added as a future feature!


### Feedback & issues reporting
Coming Soon


### Technical description <a name="sixth"></a>
1. Preprocessing
	1. Retrieves compatible files from given directory
	2. Parse and clean texts of headers/footers/annotations/references
2. Query processing
	1. Naive search for relevant docs with TF-IDF
	2. Fit query and passages using model pre-trained on Wiki texts and fine-tuned on Squad tasks, with span classification head
	3. Retrieve cross entropy losses to score passage fit and embedding vectors to compute argmax'es for answer spans
3. Model specifications
	1. Name: ALBERT base
	2. Vocabulary amount: 30,000
	3. Training data: English wikipedia, Squad dataset


### Version Releases
- v0.1 [13-Oct-2020]: debut for alpha testing
	- *features available*
		1. Extract clean texts from PDFs
		2. Return 5 top matching answers to your query

#### *Notes*
1. Sapling's internal model was trained to understand public domain language and has not been trained on domain specific language, such as Political Science or Arts. That may reduce accuracy of answers slightly, but this limitation will be improved in future releases based on user feedbacks. <a name="note1"></a>
2. Sapling has not yet been tested to its limit, but will perform slower when given hundreds of files. Performance is also machine dependant: processor speed, memory size and availability of Cuda-GPUs. <a name="note2"></a>

#### Ideas for the future:
- *Features*
	- [ ] ability to change the number of results returned
	- [ ] improve search speed with multi-thread processing
	- [ ] tidier preprocessing of PDF headers, footers and citations
	- [ ] web-based UI
	- [ ] OCR capability for unparsable PDFs
	- [ ] extract text from docx files
	- [ ] save outputs
	- [ ] combine multiple directories as a common knowledge base

- *Bug fixes*
	- [x] Segmentation fault 11 - fix memory handling with joblib