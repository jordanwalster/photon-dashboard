# Photon Dashboard - QA Testing Matrix

![Photon Logo](/logo.png)

This document outlines the test plan for the Photon Dashboard application to ensure all features are working as expected.

| Feature | Test Case | Expected Result |
| :--- | :--- | :--- |
| **Image Upload** | Upload a single JPG image. | Image appears in the main gallery. |
| | Upload multiple images (JPG, PNG, GIF) at once. | All images appear in the main gallery. |
| | Upload an image into a specific folder. | Image appears inside the selected folder. |
| | Attempt to upload an unsupported file type (e.g., .txt). | An error message is displayed, and the file is not uploaded. |
| **Image Deletion** | Send a single image to the trash. | Image is removed from the main gallery and appears in the Trash view. |
| | Send multiple selected images to the trash. | All selected images are moved to the Trash view. |
| | Permanently delete an image from the trash. | Image is permanently removed and cannot be restored. |
| | Permanently delete multiple images from the trash. | All selected images are permanently removed. |
| | Empty the entire trash. | All images in the trash are permanently deleted. |
| **Image Restoration** | Restore a single image from the trash. | Image is moved back to its original location in the gallery. |
| | Restore multiple selected images from the trash. | All selected images are moved back to their original locations. |
| | Restore all images from the trash. | All images are moved back to their original locations. |
| **Image Renaming** | Rename an image with a valid name. | The image's name is updated in the gallery and on the filesystem. |
| | Attempt to rename an image with special characters or an empty name. | An error is shown, and the name is not changed. |
| **Image Privacy** | Make a single image private. | The image is marked as private and is only visible when the 'Private' filter is active. |
| | Make multiple selected images private. | All selected images are marked as private. |
| | Make a private image public. | The image is no longer marked as private. |
| **Tagging** | Create a new tag. | The new tag appears in the tags sidebar. |
| | Assign a single tag to an image. | The tag is associated with the image. Filtering by this tag shows the image. |
| | Assign multiple tags to an image. | All selected tags are associated with the image. |
| | Assign a tag to multiple selected images. | The tag is associated with all selected images. |
| | Remove a tag from an image. | The tag is no longer associated with the image. |
| | Delete a tag. | The tag is removed from the system and from all images it was assigned to. |
| **Folder Management** | Create a new folder. | The new folder appears in the folders sidebar. |
| | Rename a folder. | The folder's name is updated in the sidebar and on the filesystem. |
| | Move images to a folder. | The selected images are moved into the target folder. |
| | Delete a folder. | The folder is removed. An appropriate prompt should handle what happens to the images inside. |
| **Image Download** | Download a single image. | The original, full-resolution image is downloaded. |
| | Download multiple selected images. | A ZIP file containing the selected images is created and downloaded. |
| | Download a folder as a ZIP file. | A ZIP file containing all images in the folder is downloaded. |
| **Background Tasks** | Verify image caching. | Thumbnails are generated and stored in `data/.cache/`. Subsequent loads are faster. |
| | Verify update check. | The application correctly checks for new versions on startup. |
| **UI & Layout** | Toggle sidebar visibility (Folders/Tags). | The corresponding sidebar section expands or collapses. The state is saved in cookies. |
| | Change number of columns. | The gallery grid updates to show the selected number of columns. The state is saved in cookies. |
| | Responsive Design - Mobile View | The layout adapts to a small screen, and all functionality is accessible. |
| | Responsive Design - Tablet View | The layout adapts to a medium screen. |

