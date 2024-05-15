### Headlines Mobile Application
<img width="1200" alt="cover" src="https://github.com/nicktheodoridisiOS/Headlines/assets/122683142/4def2783-233e-44f9-93cd-87fa6b959d5b">

### About Application
Headlines, an iOS app developed in Swift, serves as a dynamic news hub, keeping users informed with curated top stories and allowing personalization of news feeds. It enables seamless sharing of articles and offers saving favorite pieces to a personal library.

### User Preferences
<img width="1200" alt="preferences" src="https://github.com/nicktheodoridisiOS/Headlines/assets/122683142/ac127924-55c4-4358-9885-04cacefbcd10">

### Dark Mode Display
<img width="1200" alt="display" src="https://github.com/nicktheodoridisiOS/Headlines/assets/122683142/0005c965-1e77-4b92-b2a8-972a8c1029b6">

### Persist Data and Data Synchronization
<img width="80" alt="preferences" src="https://developer.apple.com/assets/elements/icons/swiftdata/swiftdata-96x96_2x.png">

For persistent data and data synchronization, the  [SwiftData](https://developer.apple.com/xcode/swiftdata/) framework was used. This way, the user can store their data by synchronizing it across multiple devices with the same account credentials.
```swift
@Model
public class Article {
    @Attribute(.unique) public var id: UUID = UUID()
    var uri: String
    var section: String
    var title: String
    var abstract: String
    var author: String
    var publishedDate: String
    var imageURL: String
    var link: String
    
    init(uri: String, section: String, title: String, abstract: String, author: String, publishedDate: String, imageURL: String, link: String) {
        self.uri = uri
        self.section = section
        self.title = title
        self.abstract = abstract
        self.author = author
        self.publishedDate = publishedDate
        self.imageURL = imageURL
        self.link = link
    }
}
```

### API Reference
For the implementation of Headlines application, I utilized [TheNewYorkTimes](https://developer.nytimes.com/apis) API which provides endpoints for searching articles, retrieving top stories and more.

### Top Stories Endpoint Call Example
| Parameter | Type     | Value |Description                |
| :-------- | :------- | :-------|:------------------------- |
| `api_key` | `string` |myApiKey |**Required** |
| `section` | `string` |world |**Required**|

```https
  GET https://api.nytimes.com/svc/topstories/v2/world.json?api-key=myApiKey
```
This will return (with JSON format) the top stories from the selected category from the articles of The New York Times:
```json
{
    "status": "OK",
    "copyright": "Copyright (c) 2024 The New York Times Company. All Rights Reserved.",
    "section": "World News",
    "last_updated": "2024-05-13T09:59:16-04:00",
    "num_results": 37,
    "results": [
        {
            "section": "",
            "subsection": "",
            "title": "Middle East Crisis: Anger and Protests Shadow Israel’s Memorial Day",
            "abstract": "Hecklers assailed Prime Minister Benjamin Netanyahu and other leaders as tensions over the Oct. 7 attacks and the Gaza war flared on one of Israel’s most solemn holidays.",
            "url": "https://www.nytimes.com/live/2024/05/13/world/israel-gaza-war-hamas-rafah",
            "uri": "nyt://promo/99de9cc4-4e4d-59ac-85e1-227bd85e55a2",
            "byline": "",
            "item_type": "Promo",
            "updated_date": "2024-05-13T13:29:00-04:00",
            "created_date": "2024-05-13T05:55:34-04:00",
            "published_date": "2024-05-13T05:55:34-04:00",
            "material_type_facet": "",
            "kicker": "",
            "des_facet": [],
            "org_facet": [],
            "per_facet": [],
            "geo_facet": [],
            "multimedia": [
                {
                    "url": "https://static01.nyt.com/images/2024/05/13/multimedia/13mideast-crisis-promo-130pm-cvfb/13mideast-crisis-promo-130pm-cvfb-superJumbo.jpg",
                    "format": "Super Jumbo",
                    "height": 1365,
                    "width": 2048,
                    "type": "image",
                    "subtype": "photo",
                    "caption": "",
                    "copyright": "Leo Correa/Associated Press"
                },
                {
                    "url": "https://static01.nyt.com/images/2024/05/13/multimedia/13mideast-crisis-promo-130pm-cvfb/13mideast-crisis-promo-130pm-cvfb-threeByTwoSmallAt2X.jpg",
                    "format": "threeByTwoSmallAt2X",
                    "height": 400,
                    "width": 600,
                    "type": "image",
                    "subtype": "photo",
                    "caption": "",
                    "copyright": "Leo Correa/Associated Press"
                },
                {
                    "url": "https://static01.nyt.com/images/2024/05/13/multimedia/13mideast-crisis-promo-130pm-cvfb/13mideast-crisis-promo-130pm-cvfb-thumbLarge.jpg",
                    "format": "Large Thumbnail",
                    "height": 150,
                    "width": 150,
                    "type": "image",
                    "subtype": "photo",
                    "caption": "",
                    "copyright": "Leo Correa/Associated Press"
                }
            ],
            "short_url": ""
        }
      ]
}
```
### Project Tools
|Xcode|GitHub|Figma|Postman|
|:---:|:---:|:---:|:---:|
|<img width="60" alt="mode" src="https://cdn.jim-nielsen.com/macos/512/xcode-2020-11-11.png?rf=1024">|<img width="60" alt="mode" src="https://cdn.jim-nielsen.com/macos/512/github-desktop-2021-05-20.png?rf=1024">|<img width="60" alt="mode" src="https://cdn.jim-nielsen.com/macos/512/figma-2021-05-05.png?rf=1024">|<img width="60" alt="mode" src="https://www.dockhunt.com/_next/image?url=https%3A%2F%2Fdockhunt-images.nyc3.cdn.digitaloceanspaces.com%2F04e04350-1ef9-40d5-893f-aa743ad3435c&w=256&q=75">|

### Programming Stack
|Swift|SwiftUI|SwiftData|
|:---:|:---:|:---:|
|<img width="60" alt="mode" src="https://developer.apple.com/assets/elements/icons/swift/swift-96x96_2x.png">|<img width="60" alt="mode" src="https://developer.apple.com/assets/elements/icons/swiftui/swiftui-128x128_2x.png">|<img width="60" alt="mode" src="https://developer.apple.com/assets/elements/icons/swiftdata/swiftdata-96x96_2x.png">|

### Note
  The reason this particular project doesn't have source code is because I want it to remain private. However, I still want to present my work through this README file. For any questions or inquiries, feel free to contact me. You can find contact details below.

### Contact
I'm always open to questions, suggestions and comments. If you have any questions or need assistance, feel free to contact me at [nicktheodoridiscontact@gmail.com](mailto:nicktheodoridiscontact@gmail.com) or through my GitHub account.

### Socials

Follow me on social media for the latest news and updates:

- Twitter: [nickiOSDev](https://twitter.com/nickiOSDev)
- Instagram: [nickmadethisone](https://www.instagram.com/nickmadethisone/)
- LinkedIn: [Nikolaos Theodoridis](https://www.linkedin.com/in/nikolaostheodoridis/)

### License
This project is distributed under the [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).

This means you can use, modify and share this work under the following conditions:
- You must attribute the original creator (attribution).
- You may not use this work for commercial purposes (non-commercial use).
