# 配置

这里主要讲 `book.json` 的配置及参数，gitbook 使用该文件来配置整本书的基本信息，结构，使用的插件等等信息，这是一个非常重要的配置文件。

这个配置文件使用 json 格式，配置非常简单，参考官方解释即可。

## reference

这是我的`book.json`的配置
```json
{
    "title": "Locus's Notebook",
    "author": "locus",
    "description": "学习知识，总结经验",
    "keywords": "markdown,gitbook,",
    "language": "zh-hans",
    "styles": {
        "website": "./styles/website.css"
    },
    "structure": {
        "readme": "README.md"
    },
    "introduction": {
        "path": "README.md",
        "title": "Gitbook使用入门概述"
    },
    "links": {
        "home": false,
        "about": false,
        "issues": false,
        "contribute": false,
        "sidebar": {
            "我的Blog": "https://byto.top"
        }
    },

    "plugins": [
    	"editlink",
        "splitter",
        "image-captions",
        "expandable-chapters-small",
        "github",
        "github-buttons",
        "donate",
        "anchor-navigation-ex",
        "favicon",
        "multipart",
        "codeblock-filename",
	    "localized-footer",
        "-lunr",
        "-search",
        "search-pro",
        "sitemap",
        "highlight"
    ],
    "pluginsConfig":{
        "theme-default": {
          "showLevel": true
        },
        "anchor-navigation-ex": {
            "showLevel": false
        },
	    "editlink": {
	      "base": "https://github.com/tkspuk",
	      "label": "编辑本页",
	      "multilingual": false
        },
        "image-captions": {
            "caption": "Image - _CAPTION_",
            "align": "center"
        },
        "expandable-chapters-small": {},
        "github": {
            "url": "https://github.com/tkspuk"
        },
        "github-buttons": {
            "buttons": [{
                "user": "tkspuk",
                "repo": "mybook",
                "type": "star",
                "size": "small",
                "count": true
                }
            ]
        },
        "sitemap": {
            "hostname": "https://byto.top/"
        },
        "search-pro": {
            "cutWordLib": "nodejieba"
        },
        "donate": {
            "wechat": "./imgs/wechat.png",
            "title": "对你有帮助",
            "button": "赞赏",
            "WeChatText": "感谢感谢"
        },
        "localized-footer": {
            "hline": true,
            "filename": "./FOOTER.md"
        },

    "pdf": {
        "toc": true,
        "pageNumbers": true,
        "fontSize": 12,
        "paperSize": "a4",
        "margin": {
          "right": 62,
          "left": 62,
          "top": 36,
          "bottom": 36
        }
    },   
	"favicon":{
            "shortcut": "./source/images/favicon.jpg",
            "bookmark": "./source/images/favicon.jpg",
            "appleTouch": "./source/images/apple-touch-icon.jpg",
            "appleTouchMore": {
                "120x120": "./source/images/apple-touch-icon.jpg",
                "180x180": "./source/images/apple-touch-icon.jpg"
            }
        }
    }
}

```
