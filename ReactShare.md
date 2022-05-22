### Installation
```bash
npm install react-share --save
```

### Components to Import
```javascript
import {
  EmailShareButton,
  FacebookShareButton,
  HatenaShareButton,
  InstapaperShareButton,
  LineShareButton,
  LinkedinShareButton,
  LivejournalShareButton,
  MailruShareButton,
  OKShareButton,
  PinterestShareButton,
  PocketShareButton,
  RedditShareButton,
  TelegramShareButton,
  TumblrShareButton,
  TwitterShareButton,
  ViberShareButton,
  VKShareButton,
  WhatsappShareButton,
  WorkplaceShareButton
} from "react-share";
```

### How to use facebook share
```javascript
import { FacebookShareButton, FacebookIcon } from 'react-share'
<FacebookShareButton
    quote={item.title}
    hashtag='#iltpusa'
    url={`iltp2022.netlify.app/news/${id}}`}
>
    <FacebookIcon
      logoFillColor='black'
      round={true}
      size={40}
    />
</FacebookShareButton>
```

# Source
https://www.npmjs.com/package/react-share
