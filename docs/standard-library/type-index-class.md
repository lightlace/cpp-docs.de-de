---
title: type_index-Klasse
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: b30c9719957b9ffc5f3ce17692eb90c1b266ae0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447053"
---
# <a name="typeindex-class"></a>type_index-Klasse

Die `type_index`-Klasse umschließt einen Zeiger auf die [type_info-Klasse](../cpp/type-info-class.md), um die Indizierung an solche Objekte zu unterstützen.

class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };

Der Konstruktor initialisiert `ptr` zu `&tinfo`.

`name` gibt `ptr->name()` zurück.

`hash_code` gibt `ptr->hash_code().` zurück

`operator==` gibt `*ptr == right.ptr` zurück.

`operator!=` gibt `!(*this == right)` zurück.

`operator<` gibt `*ptr->before(*right.ptr)` zurück.

`operator<=` gibt `!(right < *this).` zurück

`operator>` gibt `right < *this` zurück.

`operator>=` gibt `!(*this < right)` zurück.

## <a name="see-also"></a>Siehe auch

[Laufzeit-Typinformationen](../cpp/run-time-type-information.md)\
[\<typeindex>](../standard-library/typeindex.md)
