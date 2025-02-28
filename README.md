# Overview

The `FileManager` component for Qodly Studio provides a comprehensive file management interface. It allows users to navigate, view, and manage a hierarchical structure of files and folders directly within the Qodly Studio environment. The component supports viewing various file types including:

- Images: .jpg, .jpeg, .png, .gif, .webp, .svg
- Videos: .mp4, .webm, .ogg
- Documents: .pdf, .doc, .docx, .xls, .xlsx, .ppt, .pptx, .txt
- Audio: .mp3, .wav, .ogg

For implementation details, see src/components/FileManager/FileManager.render.tsx

## FileManager

A robust file management component with advanced navigation and file operations.
![fileManager](public/fileManager.png)

### Datasource

| Name       | Type             | Required | Description                                                                                                                                                        |
| ---------- | ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Datasource | array of objects | Yes      | The component expects an array of file and folder objects. Each object must have properties defining its type (file or folder), name, size, and lastModified date. |

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
        "name": "Budget.xlsx",
        "type": "file",
        "lastModified": "2024-08-10T12:00:00Z",
        "size": 85,
        "path": "https://sample-videos.com/xls/Sample-Spreadsheet-10-rows.xls"
      },
      {
        "name": "Report.docx",
        "type": "file",
        "lastModified": "2024-08-12T15:30:00Z",
        "size": 160,
        "path": "https://sample-videos.com/doc/Sample-doc-file-100kb.doc"
      },
      {
        "name": "Presentation.ppt",
        "type": "file",
        "lastModified": "2024-08-05T13:00:00Z",
        "size": 500,
        "path": "https://sample-videos.com/ppt/Sample-PPT-File-500kb.ppt"
      },
      {
        "name": "Sample-text-file.txt",
        "type": "file",
        "lastModified": "2025-02-28T00:00:00Z",
        "size": 10,
        "path": "https://sample-videos.com/text/Sample-text-file-10kb.txt"
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
                "size": 200,
                "path": "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
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
        "size": 3000,
        "path": "https://picsum.photos/seed/picsum/200/300"
      },
      {
        "name": "Landscape.jpg",
        "type": "file",
        "lastModified": "2024-07-22T08:45:00Z",
        "size": 2800,
        "path": "https://picsum.photos/seed/picsum/200/400"
      },
      {
        "name": "Cityscape.jpg",
        "type": "file",
        "lastModified": "2024-07-18T14:20:00Z",
        "size": 3200,
        "path": "https://picsum.photos/seed/picsum/300/300"
      },
      {
        "name": "Nature.jpg",
        "type": "file",
        "lastModified": "2024-07-15T09:10:00Z",
        "size": 2900,
        "path": "https://picsum.photos/seed/picsum/400/200"
      }
    ]
  },
  {
    "name": "Media",
    "type": "folder",
    "children": [
      {
        "name": "Audio",
        "type": "folder",
        "children": [
          {
            "name": "CrowdCheering.mp3",
            "type": "file",
            "lastModified": "2024-07-10T12:00:00Z",
            "size": 2500,
            "path": "https://sample-videos.com/audio/mp3/crowd-cheering.mp3"
          }
        ]
      },
      {
        "name": "Videos",
        "type": "folder",
        "children": [
          {
            "name": "BigBuckBunny.mp4",
            "type": "file",
            "lastModified": "2024-06-30T16:00:00Z",
            "size": 1024,
            "path": "https://sample-videos.com/video321/mp4/720/big_buck_bunny_720p_1mb.mp4"
          }
        ]
      }
    ]
  }
]
```

## Actions

### `onFileClick`

**Description:** Callback function triggered when a file item is clicked. It receives the clicked file item as an argument, which allows for custom handling of file selections, such as displaying file details or performing other actions.

Example to get File details

```
exposed function clickFile ()
	var event, fileData : object

	event = webEvent
	fileData = event.data
```

### `onFileRightClick`

**Description:** Callback function triggered when a file item is right-clicked. It receives the clicked file item as an argument, enabling custom actions such as showing a context menu, displaying file details, or performing specific operations.

Example to get File details

```
exposed function clickFile ()
	var event, fileData : object

	event = webEvent
	fileData = event.data
```

### `onFolderClick`

**Description:** Callback function triggered when a folder item is clicked. It receives the clicked folder item as an argument, enabling actions such as navigating into the folder or performing other folder-specific operations.

Example to get Folder details

```
exposed function clickFolder ()
	var event, folderData : object

	event = webEvent
	folderData = event.data
```
