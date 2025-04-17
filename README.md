# AI Google Presentation Generator
Automatize the creation of Google presentations with LLM (before Google releases an official version about it...):

A Python script that automatically generates professionally styled Google Slides presentations using Google's Gemini AI and the Google Slides API.

## Overview

This tool uses AI to transform a simple topic into a complete, professionally formatted Google Slides presentation. Just provide a topic, and the script will:

1. Generate comprehensive slide content using Gemini AI
2. Create a new Google Slides presentation
3. Apply professional styling and formatting
4. Add visual elements like decorative shapes with relevant text
5. Optimize text layout and formatting

## Features

- **AI-Powered Content Generation**: Uses Google's Gemini AI to create detailed, structured slide content
- **Professional Styling**: Automatically formats text, applies consistent color schemes, and optimizes layout
- **Interactive Elements**: Adds decorative shapes with key phrases relevant to your topic
- **Text Formatting**: Automatically applies bold formatting to key terms in bullet points
- **Hierarchical Structure**: Creates a logical presentation flow with title and content slides
- **Complete Automation**: Handles the entire process from content creation to final styling

## Requirements

- Python 3.6+
- Google Cloud Platform account with Google Slides API enabled
- Google Gemini API key
- Required Python packages (see Installation)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/elmoBG8/ai-google-presentation-generator.git
   cd ai-google-presentation-generator
   ```

2. Install required packages:
   ```
   pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib google-genai
   ```

3. Create OAuth 2.0 credentials:
   - Go to the [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project or select an existing one
   - Enable the Google Slides API
   - Create OAuth 2.0 credentials (Desktop application)
   - Download the credentials JSON file and save it as `credentials.json` in the script directory

4. Get a Gemini API key:
   - Go to [Google AI Studio](https://ai.google.dev/)
   - Create a new API key
   - Add your key to the script (see Configuration)

## Configuration

1. Open the script and set your Gemini API key:
   ```python
   GEMINI_API_KEY = "your-api-key-here"
   ```

2. Make sure your `credentials.json` file is in the same directory as the script

3. Create a `topic.txt` file with your presentation topic (e.g., "Sustainable Urban Development")

## Usage

1. Prepare your environment:
   - Ensure `credentials.json` is present
   - Create `topic.txt` with your desired presentation topic

2. Run the script:
   ```
   python presentation_generator.py
   ```

3. The first time you run the script, it will:
   - Open a browser window requesting authorization
   - Ask you to log in to your Google account
   - Request permission to access Google Slides
   - After granting permission, the token will be saved for future use

4. The script will generate the presentation and provide a link to access it in your Google Drive

## How It Works

1. **Content Generation**: The script sends your topic to Gemini AI with detailed instructions to create professional slide content structured as JSON
2. **Authentication**: Connects to Google Slides API using OAuth 2.0
3. **Presentation Creation**: Creates a new Google Slides presentation
4. **Content Insertion**: Inserts the AI-generated content into appropriate placeholders
5. **Styling Generation**: Creates a custom style scheme based on your topic
6. **Style Application**: Applies fonts, colors, and formatting throughout the presentation
7. **Layout Optimization**: Adjusts spacing, alignment, and text formatting
8. **Visual Enhancement**: Adds decorative elements with relevant keywords

## Troubleshooting

- **Authentication Issues**: Delete the `token.pickle` file and run the script again to re-authenticate
- **API Rate Limits**: If you hit rate limits, the script includes delays to prevent this, but you may need to increase the delay times
- **Missing Credentials**: Ensure your `credentials.json` file is in the correct location and properly formatted
- **Content Generation Failures**: Check your Gemini API key and internet connection
- **Styling Problems**: The script logs detailed information about each step; check the logs for specific errors

## Logging

The script provides detailed logging information to help track the generation process and identify any issues. Logs include:
- Content generation details
- Authentication steps
- Slide creation progress
- Styling application
- Any errors encountered

## Limitations

- The quality of generated content depends on the Gemini AI model
- Some complex formatting may not be perfectly applied
- Very specific or niche topics might result in more generic content
- The script has built-in delays to avoid API rate limits which may make the process take a few minutes

## Future Improvements

- Support for image generation and insertion
- More customization options for styling
- Templates for different presentation types
- Support for charts and graphs
- Export options to PDF or other formats

## License

[MIT License](LICENSE)

## Acknowledgements

- Google Gemini API for content generation
- Google Slides API for presentation creation
- All the contributors to the Google API Python Client

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or to Fork it.
