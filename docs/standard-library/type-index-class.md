---
title: type_index-Klasse
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 8807a041ab1c6ef47a9c3c12dac2688f121f6cfa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278961"
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

[Laufzeit-Typinformationen](../cpp/run-time-type-information.md)<br/>
[\<typeindex>](../standard-library/typeindex.md)<br/>
