---
title: Importlib (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 29c7df8fbedbd107a9bb0b05466addc4672fc555
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409379"
---
# <a name="importlib"></a>importlib

Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.

## <a name="syntax"></a>Syntax

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>Parameter

*tlb_file*<br/>
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

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)