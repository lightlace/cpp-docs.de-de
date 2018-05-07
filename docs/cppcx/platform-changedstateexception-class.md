---
title: 'Platform:: changedstateexception-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04daf6229ffa3f5ce41087a34ab53d92e3a1361c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException-Klasse
Wird ausgelöst, wenn der interne Zustand eines Objekts geändert wurde und damit die Ergebnisse der Methode ungültig wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel, in dem diese Ausnahme ausgelöst wird, ist, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde, wodurch die Ergebnisse der Methode ungültig werden.  
  
 Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)