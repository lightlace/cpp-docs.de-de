---
title: UUID (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: uuid_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c999b429cb789167eeb754b6f11a8b3d90c28642
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft-spezifisch**  
  
 Der Compiler fügt eine GUID an eine Klasse oder Struktur an, die mit dem `uuid`-Attribut deklariert oder definiert ist (nur vollständige COM-Objektdefinitionen).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__declspec( uuid("ComObjectGUID") ) declarator  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `uuid`-Attribut nimmt eine Zeichenfolge als sein Argument an. Diese Zeichenfolge gibt eine GUID im normalen Registrierungsformat mit oder ohne die **{}** Trennzeichen. Zum Beispiel:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Dieses Attribut kann in einer Neudeklaration angewendet werden. Dadurch können die Systemheader die Definitionen von Schnittstellen bereitstellen, wie **IUnknown**, und die Neudeklaration in einem anderen Header (z. B. \<comdef.h >) zum Angeben der GUID.  
  
 Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) angewendet werden können, um die Konstante abzurufen, GUID, die an einen benutzerdefinierten Typ angefügt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)