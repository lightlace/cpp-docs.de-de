---
title: Emitidl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4c66ba8c49a405f9fdd93b1652626ab47488a53
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876591"
---
# <a name="emitidl"></a>emitidl
Gibt an, ob alle nachfolgenden IDL-Attribute, verarbeitet und in der generierten IDL-Datei abgelegt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
[ emitidl(state, defaultimports=boolean) ];
```  
  
### <a name="parameters"></a>Parameter  
*state*  
Einen der folgenden Werte möglich: **"true"**, **"false"**, **erzwungen**, **eingeschränkte**, **Push**, oder **pop**.  
  
-   Wenn **"true"**, die IDL-Attribute, Kategorie in einer Quellcodedatei gefunden werden, werden in der generierten IDL-Datei. Dies ist die Standardeinstellung für **Emitidl**.  
  
-   Wenn **"false"**, die IDL-Attribute, Kategorie in einer Quellcodedatei festgestellt werden nicht in der generierten IDL-Datei platziert.  
  
-   Wenn **eingeschränkte**, können Sie die IDL-Attribute werden in der Datei ohne eine [Modul](../windows/module-cpp.md) Attribut. Der Compiler löst keine IDL-Datei.  
  
-   Wenn **erzwungen**, überschreibt einen nachfolgenden **eingeschränkte** -Attribut, das eine Datei haben muss eine **Modul** Attribut treten IDL-Attribute in der Datei.  
  
-   **Push** können Sie die aktuelle speichern **Emitidl** Einstellungen in ein internes **Emitidl** Stapel und **pop** ermöglicht Ihnen das Festlegen **Emitidl**an, der Wert am oberen Rand der internen **Emitidl** Stapel.  
  
`defaultimports=`*boolesche* \(optional)  
-   Wenn *booleschen* ist **"true"**, docobj.idl in der generierten IDL-Datei importiert wird. Auch wenn eine IDL-Datei mit dem gleichen Namen wie eine .h-, die Sie Datei `#include` in Ihrer Datenquelle Code im selben Verzeichnis wie die .h-Datei gefunden wird, dann der generierten IDL-Datei enthält eine Import-Anweisung für diese IDL-Datei.  
  
-   Wenn *booleschen* ist **"false"**, docobj.idl ist nicht in der generierten IDL-Datei importiert. Sie müssen explizit importieren .idl-Dateien mit [importieren](../windows/import.md).  
  
## <a name="remarks"></a>Hinweise  
Nach der **Emitidl** C++-Attribut in einer Quellcodedatei festgestellt wird, werden Attribute der IDL-Kategorie in der generierten IDL-Datei abgelegt. Es ist keine **Emitidl** IDL-Attribute in der Quelldatei für die Code-Attribut werden in der generierten IDL-Datei ausgegeben.  
  
Es ist möglich, mehrere **Emitidl** Attribute in einer Quellcodedatei. Wenn `[emitidl(false)];` festgestellt wird, in einer Datei ohne eine nachfolgende `[emitidl(true)];`, und klicken Sie dann keine Attribute in der generierten IDL-Datei verarbeitet werden.  
  
Jedes Mal, die der Compiler eine neue Datei erkennt **Emitidl** implizit festgelegt wird, um **"true"**.  
  
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
[Attributbeispiele](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)