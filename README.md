# Overview

The `FileManager` component for Qodly Studio provides a comprehensive file management interface. It allows users to navigate, view, and manage a hierarchical structure of files and folders directly within the Qodly Studio environment. The component supports searching, sorting, enhancing the overall file management experience.

## FileManager

A robust file management component with advanced navigation and file operations.
![fileManager](public/fileManager.png)

### Datasource

| Name       | Type             | Required | Description                                                                                                                                                        |
| ---------- | ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Datasource | array of objects | Yes      | The component expects an array of file and folder objects. Each object must have properties defining its type (file or folder), name, size, and lastModified date. |
|            |

**Some examples of data in this case:**

```json
[
  {
    "name": "Documents",
    "type": "folder",
    "children": [
      {
        "name": "Resume.pdf",
        "type": "file",
        "lastModified": "2024-08-20T14:30:00Z",
        "size": 120,
        "path": "https://hutchesonlab.fiu.edu/wp-content/uploads/sample-pdf.pdf"
      },
      {
        "name": "CoverLetter.pdf",
        "type": "file",
        "lastModified": "2024-08-18T09:00:00Z",
        "size": 45,
        "path": "https://pdfobject.com/pdf/sample.pdf"
      },
      {
        "name": "Projects",
        "type": "folder",
        "children": [
          {
            "name": "Project1",
            "type": "folder",
            "children": [
              {
                "name": "Project1_Document.pdf",
                "type": "file",
                "lastModified": "2024-08-15T11:00:00Z",
                "size": 200
              }
            ]
          },
          {
            "name": "Project2",
            "type": "folder",
            "children": []
          }
        ]
      }
    ]
  },
  {
    "name": "Images",
    "type": "folder",
    "children": [
      {
        "name": "Vacation.jpg",
        "type": "file",
        "lastModified": "2024-07-25T10:00:00Z",
        "size": 3000
      }
    ]
  }
]
```

## Actions

### `onFileClick`

**Type:** `(item: IFileItem) => void`

**Description:** Callback function triggered when a file item is clicked. It receives the clicked file item as an argument, which allows for custom handling of file selections, such as displaying file details or performing other actions.

### `onFolderClick`

**Type:** `(item: IFileItem) => void`

**Description:** Callback function triggered when a folder item is clicked. It receives the clicked folder item as an argument, enabling actions such as navigating into the folder or performing other folder-specific operations.
