# Doctor Visit Supplements Review Tool

A single-file, offline HTML tool designed to optimize 10-minute doctor appointments. Hand your tablet to your doctor, review your supplement protocol, get "Green Light / Red Light" decisions, and generate a summary report—all without an internet connection.

## 🎯 What This Is

This is a **local-first**, **zero-dependency** web application that runs entirely in your browser. No servers, no databases, no tracking. Your data exists only in RAM and disappears when you refresh the page. Built as a "quick hack" to solve a personal pain point—efficiency in GP appointment slots.

**Author's Note:** This isn't a SaaS. It's not a startup. It's a tool that works, built by someone who got tired of wasting precious appointment time explaining supplement stacks. If it helps you too, great. If not, fork it and make it better.



## 🚀 Quick Start

1. **Download** `supplements_review.html`
2. **Open** it in any text editor (Notepad, VS Code, TextEdit, etc.)
3. **Scroll** to the `// --- USER DATA SECTION (EDIT THIS) ---` comment block
4. **Edit** your supplements list in the `MY_DATA` object
5. **Save** the file
6. **Open** it in any modern web browser (Chrome, Firefox, Safari, Edge)

That's it. No installation, no npm, no build process. Just edit and open.

## 📝 Editing Your Data

The file is structured with clear markers. **ONLY EDIT** the section marked:

```javascript
// ============================================
// --- USER DATA SECTION (EDIT THIS) ---
// ============================================
// Everything below this line is YOUR data.
// Everything above is the app logic - DO NOT EDIT.
// ============================================

const MY_DATA = {
    version: "1.9",
    patientName: "Your Name Here",
    viewMode: "desktop",  // or "tablet"
    current: [
        // Your current supplements go here
    ],
    considered: [
        // Supplements you're considering go here
    ]
};

// ============================================
// --- END OF USER DATA SECTION ---
// ============================================
// DO NOT EDIT BELOW THIS LINE
// ============================================
```

### Data Structure

Each supplement entry should follow this format:

```javascript
{
    id: 'c1',                    // Unique ID (e.g., 'c1', 'c2', 'q1')
    name: "Vitamin D3 + K2-MK7", // Supplement name
    dose: "10,000 IU + 200mcg",  // Dosage
    category: "Bone/Immune",      // Category tag
    note: "Dose too high?",       // Your note/question for the doctor
    status: 'Continue',           // Initial status (or null for "considered")
    time: 'Morning'               // Timing: 'Morning', 'Afternoon', or 'Night'
}
```

**Fields:**
- `id`: Must be unique. Use 'c1', 'c2', etc. for current supplements, 'q1', 'q2', etc. for considered items.
- `name`: The supplement name
- `dose`: Dosage information
- `category`: Optional category tag (e.g., "Performance", "Sleep/Collagen", "Heart/Brain")
- `note`: Your question or note for the doctor
- `status`: For `current` items, use `'Continue'`, `'Modify'`, or `'Discontinue'`. For `considered` items, use `null`.
- `time`: `'Morning'`, `'Afternoon'`, or `'Night'`

## 💻 How It Works

1. **Tablet Mode / Desktop Mode**: Toggle between optimized layouts for different screen sizes
2. **Review Interface**: Doctor sets Action (Continue/Discontinue/Modify), Timing, and Priority (1-5) for each item
3. **Generate Report**: Creates a formatted summary with all decisions
4. **Export**: Print to PDF or copy to clipboard

## 🔒 Privacy & Security

- **100% Offline**: No network requests, no external resources
- **No Data Storage**: Data exists only in browser RAM
- **No Tracking**: Zero analytics, zero telemetry
- **Local Only**: Open the file, use it, close it. That's it.

## 📄 License

MIT License - See the license header in `supplements_review.html` or the `LICENSE` file.

## 🛠️ Technical Details

- **Version**: 1.9
- **Dependencies**: None (zero external libraries)
- **Browser Support**: Any modern browser (Chrome, Firefox, Safari, Edge)
- **File Size**: ~10KB (single HTML file)
- **Architecture**: Monolithic HTML with embedded JavaScript and CSS

## 🤝 Contributing

Found a bug? Want to add a feature? Fork it, fix it, use it. This is open source in the truest sense—it's a tool that works, shared freely. If you make it better, share it back.

## ⚠️ Disclaimer

This tool is for informational purposes only. It does not provide medical advice. Always consult with a qualified healthcare professional before making changes to your supplement protocol.

---

**Built by:** Senior Hardware/Embedded Engineer (~20 years exp), Ex-MedTech (glucose monitoring), Deep knowledge of Medical Device Regulations (MDR).  
**Tone:** Engineer-to-engineer, authentic, slightly humorous.  
**Philosophy:** Solve the problem, ship the solution, move on.
