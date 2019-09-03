---
title: TLBID-Import Attribut
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 364fb224b0f2769cb0933e71d18ff70768189328
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216536"
---
# <a name="tlbid-import-attribute"></a>TLBID-Import Attribut

**C++Zugeschnitten**

Ermöglicht das Laden anderer Bibliotheken als der primären Typbibliothek.

## <a name="syntax"></a>Syntax

> **#Import** *Type-Library-DLL* **TLBID (** *Zahl* **)**

### <a name="parameters"></a>Parameter

*einigen*\
Die Nummer der Typbibliothek in *Type-Library-DLL*.

## <a name="remarks"></a>Hinweise

Wenn mehrere Typbibliotheken in eine einzelne DLL integriert sind, ist es möglich, andere Bibliotheken als die primäre Typbibliothek mithilfe von **TLBID**zu laden.

Beispiel:

```cpp
#import <MyResource.dll> tlbid(2)
```

identisch mit folgendem Ausdruck:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
