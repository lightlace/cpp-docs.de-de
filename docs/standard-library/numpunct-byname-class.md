---
title: numpunct_byname-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: da9259df8c527e44a4adea3a53be31b3c3ffc10b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687611"
---
# <a name="numpunct_byname-class"></a>numpunct_byname-Klasse

Die abgeleitete Klassen Vorlage beschreibt ein Objekt, das als `numpunct` Facette eines bestimmten Gebiets Schemas dienen kann und die Formatierung und Interpunktions Zeichen von numerischen und booleschen Ausdrücken ermöglicht.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>Hinweise

Das Verhalten wird durch das [named](../standard-library/locale-class.md#name)-Gebietsschema `_Locname` bestimmt. Der Konstruktor initialisiert sein Basisobjekt mit [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>(`_Refs`).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
