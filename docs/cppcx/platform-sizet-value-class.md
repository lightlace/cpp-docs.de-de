---
title: 'Platform:: sizet-Wertklasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs:
- C++
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c69bf34a7965c098f6a656907071e0899b785b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087733"
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

 ## <a name="ctor"></a>  Sizet:: Sizet-Konstruktor
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