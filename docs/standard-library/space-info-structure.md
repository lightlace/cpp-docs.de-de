---
title: space_info-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::tr2::sys::space_info
dev_langs:
- C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 77314d99a34f109e556b8583b06ce51acce288bc
ms.lasthandoff: 02/24/2017

---
# <a name="spaceinfo-structure"></a>space_info-Struktur
Enthält Informationen zu einem Volume.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct space_info    {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`unsigned long long available`|Gibt die Anzahl der Bytes an, die zum Darstellen der Daten auf dem Volume verfügbar sind.|  
|`unsigned long long capacity`|Gibt die Gesamtanzahl der Bytes an, die vom Volume dargestellt werden können.|  
|`unsigned long long free`|Gibt die Anzahl der Bytes an, die nicht zum Darstellen der Daten auf dem Volume verwendet werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Dateisystem  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [space-Funktion](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)


