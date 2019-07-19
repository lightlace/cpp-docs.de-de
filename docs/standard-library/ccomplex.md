---
title: '&lt;ccomplex&gt;'
ms.date: 07/11/2019
f1_keywords:
- <ccomplex>
- ccomplex
helpviewer_keywords:
- ccomplex header
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
ms.openlocfilehash: 5b5383b1eca4fda72f5f9e3a78637373acbcf7ab
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341142"
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;

Schließt den C++ [ \<komplexen >](complex.md)-Standard Bibliotheks Header ein.

> [!NOTE]
> Der Complex. h \<-> Header der C-Standardbibliothek \<ist nicht in ccomplex > enthalten, da er durch C++ die über Ladungen \<in komplexen > \<und cmath-> ersetzt wird. Dadurch wird der \<ccomplex-> Header redundant. Der \<Complex. h-> Header ist in C++veraltet. Der \<ccomplex-> Header ist in c++ 17 veraltet und wurde im Draft c++ 20-Standard entfernt.

## <a name="requirements"></a>Anforderungen

**Header:** \<ccomplex->

**Namespace:** std

## <a name="remarks"></a>Hinweise

Der Name `clog` \<, der in der `std` Datei "Complex. > h" deklariert wird, wird im-Namespace aufgrund möglicher Konflikte `clog` mit dem, der in [ \<iostream->](iostream.md)deklariert ist, nicht definiert.

## <a name="see-also"></a>Siehe auch

[\<komplexe >](complex.md)\
[\<cmath>](cmath.md)\
[Header Dateireferenz](cpp-standard-library-header-files.md)\
[C++Übersicht über die Standardbibliothek](cpp-standard-library-overview.md)\
[Thread Sicherheit in der C++ Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)
