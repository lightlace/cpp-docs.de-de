---
title: Importlib | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a790887f54e01cea835c6110e3d81e1c2d3afeaa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206700"
---
# <a name="importlib"></a>importlib

Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.

## <a name="syntax"></a>Syntax

```cpp
[ importlib(
   "tlb_file"
) ];
```

### <a name="parameters"></a>Parameter

*tlb_file*  
Der Name einer TLB-Datei in Anführungszeichen, die in die Typbibliothek des aktuellen Projekts importiert werden soll.

## <a name="remarks"></a>Hinweise

Die **Importlib** C++-Attribut bewirkt, dass ein `importlib` Anweisung in den bibliotheksblock der generierten IDL-Datei platziert werden. Die **Importlib** Attribut hat die gleiche Funktionalität wie die [Importlib](/windows/desktop/Midl/importlib) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt ein Beispiel zur Verwendung **Importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importidl](../windows/importidl.md)  
[include](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)