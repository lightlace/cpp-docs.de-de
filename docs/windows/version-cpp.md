---
title: Version (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.version
dev_langs: C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 757ab7a6d2c8b846a51da359c4b8dc5a72c6e9e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="version-c"></a>version (C++)
Identifiziert eine bestimmte Version mehrere Versionen einer Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *version*  
 Die Versionsnummer der Co-Klasse. Wenn nicht angegeben, wird 1.0 in der IDL-Datei gespeichert.  
  
## <a name="remarks"></a>Hinweise  
 Die **Version** C++-Attribut hat die gleiche Funktionalität wie die [Version](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL-Attribut und der generierten IDL-Datei übergeben wird.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter der [bindbare](../windows/bindable.md) Beispiel für ein Beispiel für die Verwendung von **Version**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass**|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerattribute](../windows/compiler-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
