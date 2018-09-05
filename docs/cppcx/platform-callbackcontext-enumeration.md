---
title: 'Platform:: callbackcontext-Enumeration | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b80fe7749fdb2f91e300cff007c01001edfa557
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755111"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext-Enumeration
Gibt den Threadkontext an, in dem eine Rückruffunktion (Ereignishandler) ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Member  
  
|Typcode|Beschreibung|  
|---------------|-----------------|  
|Beliebig|Die Rückruffunktion kann in jedem beliebigen Threadkontext ausgeführt werden.|  
|Gleiche Voraussetzung|Die Rückruffunktion kann nur in dem Threadkontext ausgeführt werden, der den asynchronen Vorgang gestartet hat.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client (Min.):** Windows 8  
  
 **Unterstützter Server (Min.):** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd