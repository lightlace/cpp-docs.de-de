---
title: 'Platform:: IDisposable-Schnittstelle | Microsoft Docs'
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68c5425d5d65acc194287a97068df7da15f37275
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable-Schnittstelle
Wird verwendet, um nicht verwaltete Ressourcen freizugeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>Attribute  
 **GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>Member  
 Die IDisposable-Schnittstelle erbt von der IUnknown-Schnittstelle. IDisposable verfügt auch über die folgenden Membertypen:  
  
 **Methoden**  
  
 Die IDisposable-Schnittstelle verfügt über die folgenden Methoden.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|Löschen|Wird verwendet, um nicht verwaltete Ressourcen freizugeben.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform