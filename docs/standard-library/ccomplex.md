---
title: '&lt;ccomplex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ccomplex>
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: ab9e95eb7b432a85a75d73d388ec069b0d04ac62
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517201"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

Schließt den C++-Standardbibliotheksheader [\<complex>](../standard-library/complex.md) ein, der effektiv den Standard-C-Bibliotheksheader \<complex.h> einschließt und die verknüpften Namen zum `std`-Namespace hinzufügt.

## <a name="syntax"></a>Syntax

```cpp
#include <ccomplex>
```

## <a name="remarks"></a>Hinweise

Durch Einschließen dieses Headers wird sichergestellt, dass die mit externer Bindung im Standard-C-Bibliotheksheader deklarierten Namen im `std`-Namespace deklariert werden.

Der Name `clog`, der in \<complex.h> deklariert wird, ist im `std`-Namespace aufgrund potentieller Konflikte mit dem `clog`, das in [\<iostream>](../standard-library/iostream.md) deklariert ist, nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
