---
title: UUID (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- uuid
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 80975b751b6e167573a038e55042b3546821c68f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft-spezifisch**  
  
 Der Compiler fügt eine GUID an eine Klasse oder Struktur an, die mit dem `uuid`-Attribut deklariert oder definiert ist (nur vollständige COM-Objektdefinitionen).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `uuid`-Attribut nimmt eine Zeichenfolge als sein Argument an. Diese Zeichenfolge gibt eine GUID im normalen Registrierungsformat mit oder ohne die **{}** Trennzeichen. Zum Beispiel:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Dieses Attribut kann in einer Neudeklaration angewendet werden. Dadurch können die Systemheader die Definitionen von Schnittstellen bereitstellen, wie **IUnknown**, und die Neudeklaration in einem anderen Header (z. B. COMDEF. H) zum Angeben der GUID.  
  
 Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) angewendet werden können, um die Konstante abzurufen, GUID, die an einen benutzerdefinierten Typ angefügt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
