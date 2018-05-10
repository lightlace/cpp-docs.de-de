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
ms.openlocfilehash: abe2a27a79705e9850df2c9fb54037278abd8cd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="codecvtbase-class"></a>codecvt_base-Klasse

Eine Basisklasse für die codecvt-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als **Ergebnis** gekennzeichnet ist. Dieser wird als Rückgabetyp für die Facetmemberfunktionen verwendet, um das Ergebnis einer Konvertierung anzugeben.

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

- **ok**, wenn die Konvertierung zwischen internen und externen Zeichencodierungen erfolgreich war.

- **partial**, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.

- **error**, wenn die Quellsequenz fehlerhaft formuliert ist.

- **noconv**, wenn die Funktion keine Konvertierung ausführt.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
