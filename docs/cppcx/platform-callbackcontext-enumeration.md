---
title: 'Platform:: callbackcontext-Enumeration | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::CallbackContext
dev_langs: C++
helpviewer_keywords: Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: fba35e6847339287d3fa2a3d922c0d9e481a0754
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd