# BIGACE UTF8 conversion

BIGACE uses UTF-8 encoding for storing data since release 2.5. This allows you to add all kind of languages to the same BIGACE-Installation. This means if you upgrade from an older version you need to reencode your data files.

**If you are installing BIGACE for the first time, you don't need to do anything** - BIGACE and UTF-8 will work out of the box.

You can either recode all existing pages yourself, eg. using [man>iconv](man>iconv) or [man>recode](man>recode) or use the "UTF-8 conversion helper" described below.

If you do the conversion yourself, there is a list of links to start from at the end of this article.

## Why would I need UTF-8?

BIGACE is a multi-lingual system, some of the reasons to switch to UTF-8 are:

*  If you want to support multiple languages that use different character sets on your website. For instance if you want to support both Russian and Turkish, you will need a character set that supports both. UTF-8 is then a logical choice.

*  If you need better search results or improved sorting. In some cases searching and sorting by the database can be improved by chosing UTF-8 as your character set.

*  From a technical view, its just a logical step of software improvement.

## How to convert to UTF-8?

How ever you are going to convert your data, the first thing __you have to do__ is to **CREATE A BACKUP** :!:

There are two ways:

 1.  Manually, as stated above OR ...
 2.  ... by using the [BIGACE UTF8 conversion helper](bigace/administration/utf8-conversion). 

## Examples

Below are some examples of UTF-8 characters to check your browser((copied from http://wiki.splitbrain.org/doku.php)).

Zodiac Signs: ♈ ♉ ♊ ♋ ♌ ♍ ♎ ♏ ♐ ♑ ♒ ♓

A chessboard:

 |                                                     | A | B | C | D | E | F | G | H | 
 |                                                     | - | - | - | - | - | - | - | - | 
 | 8 | ♜ | ♞ | ♝ | ♛ | ♚ | ♝ | ♞ | ♜ |
 | 7 | ♟ | ♟ | ♟ | ♟ | ♟ | ♟ | ♟ | ♟ |
 | 6 |   |    |   |   |    |   |    |   |             
 | 5 |   |    |   |   |    |   |    |   |             
 | 4 |   |    |   |   |    |   |    |   |             
 | 3 |   |    |   |   |    |   |    |   |             
 | 2 | ♙ | ♙ | ♙ | ♙ | ♙ | ♙ | ♙ | ♙ |
 | 1 | ♖ | ♘ | ♗ | ♕ | ♔ | ♗ | ♘ | ♖ |

Russian (по-русски):

    По оживлённым берегам
    Громады стройные теснятся
    Дворцов и башен; корабли
    Толпой со всех концов земли
    К богатым пристаням стремятся;

Ancient Greek:

Αρχαίο Πνεύμα Αθάνατον!  
Ἰοὺ ἰού· τὰ πάντʼ ἂν ἐξήκοι σαφῆ.
    Ὦ φῶς, τελευταῖόν σε προσϐλέψαιμι νῦν,
    ὅστις πέφασμαι φύς τʼ ἀφʼ ὧν οὐ χρῆν, ξὺν οἷς τʼ
    οὐ χρῆν ὁμιλῶν, οὕς τέ μʼ οὐκ ἔδει κτανών.

Modern Greek:
    Η σύγχρονη Ελλάδα, έχει να παρουσιάσει δυναμικό
    έργο στον τομέα του πολιτισμού, των τεχνών και
    των γραμμάτων. Αντίστοιχα δυναμική είναι η παρουσία
    των Ελλήνων επιχειρηματιών στην διεθνή οικονομική
    και βιομηχανική σκηνή.

Sanskrit:

    पशुपतिरपि तान्यहानि कृच्छ्राद्
    अगमयदद्रिसुतासमागमोत्कः । 
    कमपरमवशं न विप्रकुर्युर्
    विभुमपि तं यदमी स्पृशन्ति भावाः ॥

Hindi:

गूगल समाचार हिन्दी में 

Korean:
    한글은 아름다운 우리글입니다.
    곱고 아름답게 사용하는 것이 우리의 의무입니다.

Chinese:

    子曰：「學而時習之，不亦說乎？有朋自遠方來，不亦樂乎？
    人不知而不慍，不亦君子乎？」
    
    有子曰：「其為人也孝弟，而好犯上者，鮮矣；
    不好犯上，而好作亂者，未之有也。君子務本，本立而道生。
    孝弟也者，其為仁之本與！」

Japanese:

    「秋の田の かりほの庵の 苫をあらみ わが衣手は 露にぬれつつ」　天智天皇
    「春すぎて 夏来にけらし 白妙の 衣ほすてふ 天の香具山」　持統天皇
    「あしびきの 山鳥の尾の しだり尾の ながながし夜を ひとりかも寝む」　柿本人麻呂 

Latvian:
    
    Iedomu jaukie ideāli,
    Vecākie principi, tikla, mīla - 
    Dienas allažības priekšā
    Šķīst kā graudi akmeņstarpā.

Simplified Chinese:

    这是简体字汉语。 zhè shì jiǎn t zì hàn yǔ 

Armenian:

    Հարգանքներիս հավաստիքը Հայ Ժողովրդին:
    Ամենալավ օրենքները չեն օգնի, եթե մարդիկ բանի պետք չեն:

Hebrew:

    המשפט עם הזכוכית שאפשר לאכול בלי שזה מפריע, לא זוכר איך הוא הולך

## Stay with none-UTF8

This is not supported, if somehow possible, migrate to UTF-8!

We highly recommend migrating to UTF-8, but if you - for any reason - cannot convert your data, you have to adjust a couple of settings:

1. Change file "/system/config/config.system.php":

	:::php
	$_BIGACE['db']['character-set'] = 'latin1';


Set the character set your database uses.
The value 'latin1' is just an example! It might work for you, but you cannot rely on it, because it depends on your mysql-server settings.

2. Change all language INI files (for example "/system/language/de.ini" and "/system/language/en.ini"):

	:::ini
	charset = ISO-8859-1


The encoding to be used for delivering pages. "ISO-8859-1" was used in older version of BIGACE.

These steps need to be done after EACH future update, so please think about switching to UTF-8 once.

## Link list regarding UTF-8 conversion

There are a lot of tutorials out there, but those helped me creating the [conversion helper](bigace/administration/utf8-conversion):


*  http://www.phpwact.org/php/i18n/utf-8/mysql

*  http://www.hackszine.com/blog/archive/2007/05/mysql_database_migration_latin.html

*  http://www.orthogonalthought.com/blog/index.php/2007/05/mysql-database-migration-and-special-characters/

*  http://www.bluetwanger.de/blog/2006/11/20/mysql-and-utf-8-no-more-question-marks/

*  http://wiki.splitbrain.org/wiki:utf8

*  http://dev.mysql.com/doc/refman/5.0/en/charset-general.html

