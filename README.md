# 📋 STFormView – Powerful, Configurable Form Engine in SwiftUI

**STFormView** is a modular, fully themeable SwiftUI form system that supports a variety of field types (text, password, radio, multi-select, image/file upload, etc.), layout directions, live validation, and export to PDF.

It’s perfect for internal tools, onboarding wizards, data collection flows, or standalone form-based apps.

---

## ✨ Features

- ✅ Full support for text, number, email, password, toggle, radio, multiselect, dropdown, image & file upload
- ✅ Horizontal or vertical layout for radio & multiselect
- ✅ iOS-native file & image pickers
- ✅ Live validation with customizable error display
- ✅ PDF export of form data with auto layout
- ✅ Configurable themes (color, font, shapes, spacing, etc.)
- ✅ SwiftUI-native, stateless View model pattern
- ✅ Inline PDF previews using PDFKit
- ✅ Preview mode toggle for display-only form view
- ✅ Keyboard-aware, accessible, production-grade layout

---

## 📦 Usage Example

```swift
STFormView(
    sections: [
        FormSection(
            title: "Personal Info",
            fields: [
                .text(label: "Name", key: "name", required: true),
                .email(label: "Email", key: "email"),
                .toggle(label: "Subscribe", key: "subscribe")
            ]
        ),
        FormSection(
            title: "Preferences",
            fields: [
                .radio(label: "Gender", key: "gender", options: ["Male", "Female", "Other"], isHorizontal: true),
                .multiSelect(label: "Tech", key: "tech", options: ["Swift", "Flutter", "React"])
            ]
        )
    ],
    theme: STFormTheme.default,
    previewMode: false
) { submittedData in
    print(submittedData)
}
```

---

## 🧠 FormFieldType

Supported input types:
- `.text`, `.email`, `.number`, `.password`
- `.date`, `.toggle`, `.checkbox`
- `.radio` (horizontal/vertical)
- `.multiSelect` (horizontal/vertical)
- `.dropdown`
- `.imageUpload`
- `.fileUpload`

---

## 🖌 Theming

Theme form globally using `STFormTheme`:

```swift
STFormTheme.default = STFormTheme(
    primaryColor: .indigo,
    backgroundColor: .white,
    textColor: .black,
    labelFont: .headline,
    errorColor: .red,
    cornerRadius: 12,
    imageHeight: 100,
    imageShape: .rounded(8)
)
```

---

## 📝 PDF Export

```swift
let pdfData = FormPDFExporter.export(data: yourFormDict, title: "User Submission")
```

PDF is auto-generated with proper margins and spacing.

---

## 🔍 Preview Mode

You can set `previewMode: true` to render the form in a non-editable, display-only mode.

---

## 📁 File & Image Upload

- Integrates with native `UIImagePickerController`
- Supports `.pdf` import via `UIDocumentPicker`
- Includes inline PDF previews (`PDFKitView`)
- Image previews are shape-aware (rounded, circle, square)

---

## 📄 Dependencies

- UIKit (for file/image picker)
- PDFKit (for preview/export)
- SwiftUI 2.0+

---

## 📦 Installation

### Swift Package Manager

Paste this URL in Xcode:

```
https://github.com/yourusername/STFormView
```

---

## 📸 Screenshots

> Add here if needed (form view, dark/light themes, image upload, PDF preview)

---

## 🛠 Roadmap

- [ ] JSON-based form rendering
- [ ] Repeating groups and nested forms
- [ ] Server-driven validation logic
- [ ] Markdown-style text support
- [ ] Voice input and accessibility polish

---

## 🤝 Contributing

PRs are welcome! Please open issues for bugs, ideas, or enhancements.


---

Want a landing page or App Store-ready demo? Just ask!
