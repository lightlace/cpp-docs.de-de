---
title: bad_array_new_length-Klasse
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: b00042513364ac04b62ac7e1943d912dcb78f212
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459486"
---
# <a name="badarraynewlength-class"></a>bad_array_new_length-Klasse

Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass eine Zuordnungs Anforderung aufgrund einer Array Größe kleiner als 0 (null) oder größer als der Grenzwert nicht erfolgreich war.

## <a name="syntax"></a>Syntax

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Hinweise

Der von zurückgegebene `what` Wert ist eine von der Implementierung definierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

## <a name="requirements"></a>Anforderungen

**Header:** \<new>

## <a name="see-also"></a>Siehe auch

[Exception-Klasse](../standard-library/exception-class.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
