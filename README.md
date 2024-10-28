# StoriesWidget

The `StoriesWidget` is a Flutter widget designed to display user stories in a scrollable, Instagram-like format. It supports both images and videos with an automatic linear progress indicator, customized display duration, and a seamless experience for end-users.

## Features
- Supports image and video media types.
- Automatically calculates and displays progress for each story.
- Plays videos according to their actual duration and displays images for a configurable duration.
- Automatic looping of stories and navigation to the next story upon completion.
- Manual swipe functionality for user-initiated navigation.

## Getting Started

These instructions will guide you on setting up the project locally on your machine.

### Prerequisites

- **Flutter SDK**: [Install Flutter](https://flutter.dev/docs/get-started/install) if you haven’t already.
- **Git**: [Install Git](https://git-scm.com/downloads) if you haven’t already.
- **Supabase Account**: You’ll need a Supabase project with a table to store the stories.

### Setting Up Supabase

1. **Create a Supabase Project**: Go to [Supabase](https://supabase.io/) and set up a new project.
2. **Create the `user_stories` Table**: Create a table with the following structure:
   - `user_id` (String): User ID to associate stories.
   - `media_url` (String): URL of the media file (image or video).
   - `is_video` (Boolean): Specifies if the media is a video.
3. **API Keys**: Obtain your Supabase API URL and Key from the project’s dashboard.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/StoriesWidget.git
   cd Install dependencies:

bash
Copy code
flutter pub get
Add Supabase Credentials:

In lib/supabase_config.dart or wherever your Supabase configuration file is located:
dart
Copy code
const String SUPABASE_URL = 'your-supabase-url';
const String SUPABASE_KEY = 'your-supabase-key';
Usage
Include the StoriesWidget in your app:

dart
Copy code
import 'package:your_package_name/widgets/stories_widget.dart';

StoriesWidget(
  userId: 'user_id_here', // replace with dynamic user ID as needed
  width: MediaQuery.of(context).size.width,
  height: MediaQuery.of(context).size.height * 0.8,
)
Stories Structure:

Video: Automatically plays for the video’s duration.
Image: Displays for 7 seconds (modifiable in code).
Code Structure
Story Class: Defines the structure for each story and fetches video durations automatically.

StoryDisplayWidget: Manages story progress, swiping, and looping functionality.

StoryContentWidget: Displays the individual stories, rendering either an image or video widget based on the media type.

Progress Indicator: A dynamic progress indicator located at the top reflects the current story’s playtime and progresses based on video duration or image timeout.

Configurations
To customize the image duration, modify the Duration for images in _StoryDisplayWidgetState.startStoryProgress(), e.g.:

dart
Copy code
final Duration imageDuration = Duration(seconds: 7);
Troubleshooting
Video Progress Misalignment: Ensure the video duration is correctly fetched. If issues persist, verify the connection to Supabase and that videos are accessible via URLs.
Supabase API Errors: Double-check API URL and keys in your Supabase configuration file.
Contributions
Contributions are welcome! Feel free to open issues or submit pull requests with improvements.

License
This project is licensed under the MIT License.

arduino
Copy code

Feel free to adjust URLs, paths, or any other configuration specifics to fit your project setup!





StoriesWidget
