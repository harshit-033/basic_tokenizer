# Basic Tokenizer

## Abstract

This repository contains a basic text tokenization implementation developed to study how raw text can be converted into a sequence of smaller textual units suitable for further natural language processing tasks.

The implementation uses Python regular expressions to identify whitespace and selected punctuation marks as token boundaries. A plain-text literary document is used as the input corpus. The notebook demonstrates the tokenization process step by step, including text loading, delimiter selection, splitting, and removal of empty or whitespace-only elements.

The work is intended as an educational implementation for understanding the preprocessing stage used in NLP and language-model pipelines.

## 1. Introduction

Tokenization is the process of dividing text into smaller units called tokens. Depending on the tokenizer design, tokens may represent words, punctuation marks, subwords, or individual characters.

This repository implements a simple rule-based tokenizer using Python and regular expressions. The purpose is not to reproduce a modern production tokenizer, but to provide a transparent implementation through which the fundamental operations of text tokenization can be examined.

## 2. Objectives

The main objectives of this work are:

- To understand the basic concept of tokenization.
- To read and preprocess a raw text corpus.
- To identify words and selected punctuation marks as separate tokens.
- To use regular expressions for defining token boundaries.
- To remove empty and whitespace-only elements generated during splitting.
- To inspect the resulting token sequence for further NLP processing.

## 3. Methodology

The tokenizer follows a simple preprocessing pipeline:

```text
Raw Text
   |
   v
Read Text Corpus
   |
   v
Define Token Boundaries
   |
   v
Regular Expression Splitting
   |
   v
Remove Empty / Whitespace Tokens
   |
   v
Token Sequence
```

The implementation initially investigates whitespace-based splitting and then extends the delimiter pattern to preserve selected punctuation marks as independent tokens.

The current regular-expression pattern separates:

- Whitespace
- Comma (,)
- Period (.)
- Colon (:)
- Semicolon (;)
- Question mark (?)
- Underscore (_)
- Exclamation mark (!)
- Double quotation mark (")
- Parentheses
- Apostrophe (')
- Double hyphen (--)

After splitting, whitespace-only elements and empty strings are removed from the result.

## 4. Repository Contents

| File | Description |
|---|---|
| `TOKENIZER.ipynb` | Jupyter Notebook containing the tokenizer implementation, experiments, intermediate outputs, and observations. |
| `verdict.txt` | Text corpus used as the input for demonstrating the tokenization process. |

## 5. Implementation

The implementation is written in Python and primarily uses the standard `re` module for regular-expression based text processing.

A simplified representation of the main operation is:

```python
preprocessed = re.split(r'([,.:;?_!"()\']|--|\s)', content)
preprocessed = [item for item in preprocessed if item.strip()]
```

The use of capturing groups in the regular expression allows selected delimiters to remain visible in the resulting sequence rather than being discarded completely.

## 6. Example

For an input such as:

```text
I had, always thought Jack Gisburn.
```

the tokenizer separates words and selected punctuation into individual elements, producing a sequence conceptually similar to:

```text
I
had
,
always
thought
Jack
Gisburn
.
```

This illustrates the basic idea of converting continuous text into a structured token sequence.

## 7. Purpose and Applications

The implementation is intended primarily for educational and experimental use. It provides a simple foundation for studying:

- Text preprocessing
- Natural language processing
- Token boundaries
- Regular expressions
- Vocabulary construction
- Subsequent encoding of text into numerical representations

The tokenizer can serve as an initial step toward implementing more advanced tokenization and language-model preprocessing techniques.

## 8. Limitations

This implementation is intentionally basic and has several limitations:

- It uses manually selected punctuation rules.
- It does not implement subword tokenization such as BPE or WordPiece.
- It does not construct a vocabulary or assign token IDs.
- It does not provide a dedicated tokenizer class or reusable package interface.
- Language-specific cases, Unicode normalization, contractions, and complex punctuation are not comprehensively handled.
- It is not intended to replace optimized production tokenizers.

## 9. Requirements

The notebook requires:

- Python 3.x
- Jupyter Notebook or JupyterLab
- Python standard library module: `re`

No external Python package is required for the core implementation.

## 10. Usage

Clone the repository:

```bash
git clone https://github.com/harshit-033/basic_tokenizer.git
cd basic_tokenizer
```

Open the notebook:

```bash
jupyter notebook TOKENIZER.ipynb
```

Run the cells sequentially to observe the text loading, preprocessing, splitting, and resulting token sequence.

## 11. Conclusion

This repository presents a basic and transparent implementation of text tokenization using Python regular expressions. The work demonstrates how raw textual data can be transformed into discrete tokens by defining explicit token boundaries and applying systematic preprocessing.

Although simple compared with modern subword tokenizers, the implementation provides a practical foundation for understanding one of the first stages of NLP and language-model data preparation.

## Author

Harshit Kumar

Repository: https://github.com/harshit-033/basic_tokenizer
