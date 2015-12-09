# 配置文件寫法 #

默認簡繁轉換的配置文件 zhs2zht.ini 的內容如下：

```
title = simp_to_trad
description = Standard Configuration for Conversion from Simplified Chinese to Traditional Chinese
dict0 = OCD simp_to_trad_phrases.ocd
dict0 = OCD simp_to_trad_characters.ocd
```

title和description是可選字段，用於描述配置文件。下面每行爲一個辭典配置，格式爲：

```
dict[x] = [TEXT/OCD] [filename]
```

其中x從爲一個整數，從0開始表示 **辭典組** 的號碼；TEXT或OCD表示辭典的類型，TEXT是文本類型辭典，OCD爲由opencc\_dict工具建立索引後的類型辭典；filename爲辭典文件名。

x相同的若干行屬於同一個 **辭典組** ，視爲同一辭典，從上到下依次搜索。不同 **辭典組** 按照號碼遞增的順序，依次鏈式轉換，即文本先由原始輸入經dict0轉換後，將結果輸入到dict1轉換，然後再將結果用dict2轉換……

例如簡繁混雜到繁體的配置文件 mix2zht.ini ：

```
title = mix_to_trad
description = Standard Configuration for Conversion from Simplified-Traditional-Mixed Chinese to Traditional Chinese
dict0 = OCD trad_to_simp_characters.ocd
dict1 = OCD simp_to_trad_phrases.ocd
dict1 = OCD simp_to_trad_characters.ocd
```

輸入文本先由dict0(trad\_to\_simp\_characters.ocd)轉換，再將結果由simp\_to\_trad\_phrases.ocd和simp\_to\_trad\_characters.ocd組成的dict1轉換。在使用dict1轉換的過程中，優先在simp\_to\_trad\_phrases.ocd查找詞彙，如果沒有找到，再到simp\_to\_trad\_characters.ocd尋找。

# 辭典格式 #

TEXT類型的辭典每行格式爲
```
词汇	詞彙
```
即 詞彙1\t詞彙2

具體可以參見 https://github.com/BYVoid/OpenCC/raw/master/data/simp_to_trad/phrases.txt