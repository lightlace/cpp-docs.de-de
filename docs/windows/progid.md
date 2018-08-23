---
title: ProgID | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fff878cfecf6eb39d689c3a17c1eab0ab5c47d4f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589198"
---
# <a name="progid"></a>progid

Gibt an, die ProgID für ein COM-Objekt.

## <a name="syntax"></a>Syntax

```cpp
[ progid(
   name
) ];
```

### <a name="parameters"></a>Parameter

*name*  
Die ProgID, die das Objekt darstellt.

Versionsabhängige Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.

## <a name="remarks"></a>Hinweise

Die **progid** C++-Attribut können Sie angeben, die ProgID für ein COM-Objekt. Eine ProgID hat das Format *name1.name2.version*. Wenn Sie keinen angeben einer *Version* für ProgID, die Standardversion ist 1. Wenn Sie keinen angeben *name1.name2*, der Standardname lautet *classname.classname*. Wenn Sie keinen angeben **progid** angegeben `vi_progid`, *name1.name2* stammen aus `vi_progid` und die (nächste laufende Nummer) Version angefügt wird.

Wenn ein Attributblock, die verwendet **progid** nicht gleichzeitig verwenden **Uuid**, der Compiler überprüft die Registrierung, um festzustellen, ob eine **Uuid** vorhanden ist, für den angegebenen **progid** . Wenn **progid** nicht angegeben ist, wird die Version (und den Namen der Co-Klasse, sofern es sich bei eine Co-Klasse zu erstellen) verwendet werden, generieren eine **progid**.

**ProgID** impliziert die `coclass` -Attributs, d. h. Wenn Sie angeben, **progid**, es ist dasselbe wie beim Angeben der `coclass` und **progid** Attribute.

Die **progid** Attribut bewirkt, dass eine Klasse automatisch unter dem angegebenen Namen registriert werden. Der generierten IDL-Datei wird nicht angezeigt. die **progid** Wert.

Wenn dieses Attribut in einem Projekt, das ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Mit diesem Attribut angegebene Informationen werden zusätzlich zu den oben beschriebenen Verhalten in der `GetProgID` Funktion eingefügt werden, indem die `coclass` Attribut. Weitere Informationen finden Sie unter den [Co-Klasse](../windows/coclass.md) Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Co-Klasse](../windows/coclass.md) für ein Beispiel für die Verwendung von **progid**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[Programm-ID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/dd542719)  
