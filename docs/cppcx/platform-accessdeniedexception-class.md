---
title: 'Platform:: accessdeniedexception-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4be26bfc87be55d36954429c64094cabd6a6cf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException-Klasse
Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Ausnahme erreicht haben, stellen Sie sicher, dass Sie die entsprechende Funktion angefordert und die erforderlichen Deklarationen im Paketmanifest der App angegeben haben. Weitere Informationen finden Sie unter [COMException](../cppcx/platform-comexception-class.md) .  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)