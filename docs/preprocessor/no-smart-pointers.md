---
title: no_smart_pointers-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: 1fca3eb486ff3cfc7403c38e91855b799a698782
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220699"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers-Attribut importieren

**C++Zugeschnitten**

Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_smart_pointers**

## <a name="remarks"></a>Hinweise

Wenn Sie `#import` verwenden, rufen Sie standardmäßig die Deklaration eines intelligenten Zeigers für alle Schnittstellen in der Typbibliothek ab. Diese intelligenten Zeiger sind vom Typ [_com_ptr_t](../cpp/com-ptr-t-class.md).

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
