---
title: codecvt_base-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a471cdd63ed46e15c9ec41968ed341eefaf36963
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965391"
---
# <a name="codecvtbase-class"></a>codecvt_base-Klasse

Eine Basisklasse für die Codecvt-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, die als bezeichnet `result`wird als den Rückgabetyp für die facetmemberfunktionen um das Ergebnis einer Konvertierung anzugeben.

## <a name="syntax"></a>Syntax

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt eine Enumeration, die allen Spezialisierungen der Vorlagenklasse [codecvt](../standard-library/codecvt-class.md) gemein ist. Das Enumerationsergebnis beschreibt die möglichen Rückgabewerte [do_in](../standard-library/codecvt-class.md#do_in) oder [do_out](../standard-library/codecvt-class.md#do_out):

- `ok` Wenn die Konvertierung zwischen internen und externen zeichencodierungen erfolgreich ausgeführt wird.

- `partial` Wenn das Ziel nicht groß genug für die Konvertierung erfolgreich ausgeführt werden kann.

- `error` Wenn die Quellsequenz fehlerhaft formuliert ist gebildet werden soll.

- `noconv`, wenn die Funktion keine Konvertierung ausführt.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
