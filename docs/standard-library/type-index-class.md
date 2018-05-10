---
title: type_index-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- typeindex/std::type_index
dev_langs:
- C++
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e301b8d47c1a054a5b80bff105950d876d90b047
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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
