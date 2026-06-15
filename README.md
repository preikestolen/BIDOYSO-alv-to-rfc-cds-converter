# AI-Powered SAP ALV to RFC/CDS Converter

An AI-powered web application built to accelerate the modernization of SAP ABAP code. It converts legacy ABAP ALV reports into modern SAP CDS Views or ABAP Cloud-compatible RFCs, with built-in support for S/4HANA "Clean Core" architecture.

## 🚀 Features

- **ALV to CDS View Conversion:** Automatically extract data fetching logic (SELECT statements) and selection screen parameters from legacy ALV reports and translate them into modern ABAP CDS View Entities.
- **ALV to RFC Conversion:** Transform legacy ALV reports into modular, ABAP Cloud-compatible Remote Function Calls (RFCs) for easy integration and external consumption.
- **S/4HANA Clean Core Support:** Intelligently maps legacy SAP tables (e.g., `MARA`, `VBAK`, `BKPF`, `ACDOCA`) to their modern released SAP CDS View successors, accelerating your transition to a Clean Core architecture.
- **Dictionary Mapping Manager:** A built-in mapping dictionary where users can view and customize legacy-to-CDS table and field mappings.
- **AI Code Refinement:** Fine-tune generated code by providing follow-up instructions to the AI (e.g., "add OData annotations", "change the join type", "aggregate the amount field"). 

## 🛠️ Technology Stack

- **Frontend Framework:** React 18 with TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **Icons:** Lucide React
- **AI Integration:** Google Gemini API (`@google/genai`) 
- **Syntax Highlighting:** `react-syntax-highlighter` (or custom styling)

## 📦 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the root directory and add your Google Gemini API key:
   ```env
   GEMINI_API_KEY=your_actual_gemini_api_key
   ```
   *(Note: For production, ensure the API calls are made securely from a backend server so the API key is not exposed to the client.)*

4. **Start the development server:**
   ```bash
   npm run dev
   ```
   The application will be available at `http://localhost:3000`.

## 💡 How to Use

1. **Select a Conversion Type:** From the main dashboard, choose either "ALV to CDS" or "ALV to RFC".
2. **Paste Code:** Paste your legacy SAP ABAP ALV report code (including data fetching logic and selection screens) into the code editor.
3. **Clean Core Mode (for CDS):** Toggle "Clean Core Conversion" ON to automatically replace legacy tables with modern S/4HANA CDS Views.
4. **Convert:** Click the "Convert Code" button. The AI will analyze the code and generate the corresponding CDS View or RFC code.
5. **Refine:** If the output needs adjustment, type your instructions in the "Refinement Prompt" input and click the refresh icon to let the AI update the code.
6. **Dictionary Mapping:** In the ALV to CDS tool, click "Manage Dictionary" to review, search, and edit the rules defining how legacy tables map to CDS views.

## ⚠️ Notes for Developers

- **Gemini API:** The application uses `gemini-3.1-pro-preview` for complex code translation and schema analysis. 
- **ABAP Constraints:** The prompts are strict about ABAP syntax. For example, it enforces rules like "No functions in JOIN conditions" and "Proper use of INTO CORRESPONDING FIELDS OF TABLE" to avoid ABAP compilation errors.

## 📄 License

Please read the LICENSE file.
