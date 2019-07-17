---
title: Bad_array_new_length-Klasse
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 823da1555119735e9aa1c46aa4db2e3a47affdec
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268692"
---
# <a name="badarraynewlength-class"></a>Bad_array_new_length-Klasse

Die Klasse beschreibt eine Ausnahme ausgelöst werden, um anzugeben, dass eine zuordnungsanforderung aufgrund der Größe des Arrays, die kleiner als 0 (null) oder größer als das Limit nicht erfolgreich war.

## <a name="syntax"></a>Syntax

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Hinweise

Der Rückgabewert von `what` ist eine implementierungsdefinierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

## <a name="requirements"></a>Anforderungen

**Header:** \<new>

## <a name="see-also"></a>Siehe auch

[exception-Klasse](../standard-library/exception-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
