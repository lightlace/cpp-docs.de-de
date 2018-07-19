---
title: '&lt;fstream&gt; typedefs | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: 49c5af53c6d174e7f87f75ad8970726c526db714
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962974"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs (<fstream>-Typdefinitionen)

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a> filebuf

Ein Typ `basic_filebuf` auf **Char** Vorlagenparameter.

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_filebuf](../standard-library/basic-filebuf-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="fstream"></a> fstream

Ein Typ `basic_fstream` auf **Char** Vorlagenparameter.

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_fstream](../standard-library/basic-fstream-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="ifstream"></a> ifstream

Definiert einen Stream, der für das serielle Lesen von Einzelbyte-Zeichendaten aus einer Datei verwendet werden soll. `ifstream` ist eine Typedef, die die Vorlagenklasse spezialisiert hat `basic_ifstream` für **Char**.

Es gibt auch `wifstream`, eine Typedef, die spezialisiert hat `basic_ifstream` lesen **"wchar_t"** doppelt breiten Zeichen. Weitere Informationen finden Sie unter [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ifstream](../standard-library/basic-ifstream-class.md), Elemente vom Typ "Char" mit standardzeichenmerkmalen spezialisiert. Ein Beispiel ist

`using namespace std;`

`ifstream infile("existingtextfile.txt");`

`if (!infile.bad())`

`{`

`// Dump the contents of the file to cout.`

`cout << infile.rdbuf();`

`infile.close();`

`}`

## <a name="ofstream"></a> ofstream

Ein Typ `basic_ofstream` auf **Char** Vorlagenparameter.

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ofstream](../standard-library/basic-ofstream-class.md), die auf Elemente des Typs **Char** mit Standard-Zeichenmerkmale.

## <a name="wfstream"></a> wfstream

Ein Typ `basic_fstream` auf **"wchar_t"** Vorlagenparameter.

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_fstream](../standard-library/basic-fstream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="wifstream"></a> wifstream

Ein Typ `basic_ifstream` auf **"wchar_t"** Vorlagenparameter.

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ifstream](../standard-library/basic-ifstream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="wofstream"></a> wofstream

Ein Typ `basic_ofstream` auf **"wchar_t"** Vorlagenparameter.

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_ofstream](../standard-library/basic-ofstream-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="wfilebuf"></a> wfilebuf

Ein Typ `basic_filebuf` auf **"wchar_t"** Vorlagenparameter.

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für die Vorlagenklasse [Basic_filebuf](../standard-library/basic-filebuf-class.md), die auf Elemente des Typs **"wchar_t"** mit Standard-Zeichenmerkmale.

## <a name="see-also"></a>Siehe auch

[\<fstream>](../standard-library/fstream.md)<br/>
