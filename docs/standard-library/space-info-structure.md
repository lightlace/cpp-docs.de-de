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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: e8573fab6f0d1a1ad43a9be2e3be1ddd8f556748
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

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
 **Header:** \<Filesystem >  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [Speicherplatz](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)


