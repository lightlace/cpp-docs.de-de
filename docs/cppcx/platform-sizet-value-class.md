---
title: 'Platform:: sizet-Wertklasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs: C++
helpviewer_keywords: Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf47d911dc348b23e371175cf46fc6d677ce9f36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformsizet-value-class"></a>Platform::SizeT-Wertklasse
Stellt die Größe eines Objekts dar. SizeT ist ein Datentyp ohne Vorzeichen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class SizeT sealed : ValueType  
```  
  
### <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[SizeT::SizeT-Konstruktor](#ctor)|Initialisiert eine neue Instanz der Klasse mit dem angegebenen Wert.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

 ## <a name="ctor"></a>Sizet:: Sizet-Konstruktor
Initialisiert eine neue Instanz von SizeT mit dem angegebenen Wert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
SizeT( uint32 value1 );   SizeT( void* value2 );  
```  
  
### <a name="parameters"></a>Parameter  
 value1  
 Ein nicht signierter 32-Bit-Wert.  
  
 value2  
 Zeiger auf einen nicht signierten 32-Bit-Wert.  
  
  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)