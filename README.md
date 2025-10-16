# Multi-Agent Data Analyst Assistant

A **Streamlit-based multi-agent system** that allows users to upload documents, ask questions about the content, or generate visualizations. The system uses specialized agents for file extraction, question answering, and data visualization to provide an interactive and intelligent data analysis experience.

---

## **Features**
- Upload files: `.txt`, `.csv`, `.xlsx`, `.pdf`, `.jpg`, `.jpeg`, `.png`
- Extract text and tabular data automatically
- Answer questions about uploaded documents using **Llama-4-Maverick-17B**
- Generate visualizations (histogram, scatter, bar charts) for tabular data
- Interactive real-time interface using Streamlit
- Reset and re-upload files anytime

---

## **Architecture / Agents**
1. **FileExtractorAgent**  
   - Processes uploaded files based on type (text, tabular, PDF, image)
   - Uses `PyPDF2` for PDFs and `pytesseract` for OCR on images
   - Converts content into text or DataFrame for further processing

2. **QuestionAnsweringAgent**  
   - Uses **Together AI API** with `meta-llama/Llama-4-Maverick-17B` for answering questions
   - Handles both textual content and summarized tabular data

3. **VisualizationAgent**  
   - Generates matplotlib/seaborn plots from tabular data
   - Supports histogram, scatter, and bar chart visualizations based on natural language queries

4. **Orchestrator**  
   - Manages interactions between agents
   - Processes uploaded files, handles queries, and decides whether to generate visualizations or answers

---

## **Tech Stack**
- **Python 3.x**
- **Streamlit** – Interactive web interface
- **pandas** – Data handling and manipulation
- **matplotlib & seaborn** – Data visualization
- **PyPDF2** – PDF parsing
- **pytesseract** – OCR for image files
- **Together API** – LLM-based question answering
- **Pillow** – Image handling

---

## **How It Works**
1. **Upload File**: User uploads a supported file type.  
2. **File Processing**: FileExtractorAgent converts the file into readable content.  
3. **Query / Visualization**:  
   - For textual queries, QuestionAnsweringAgent uses Llama-4-Maverick-17B to answer questions.  
   - For visualization requests, VisualizationAgent generates plots if the content is tabular.  
4. **Interactive Feedback**: Users see answers or plots immediately in the Streamlit UI.  
5. **Reset Option**: Allows uploading a new file anytime.

---

## **Usage**
1. Clone the repository:

```bash
git clone https://github.com/your-username/Multi-Agent-Data-Analyst.git
