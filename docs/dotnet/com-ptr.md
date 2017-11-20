---
title: 'com:: PTR | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ptr
dev_langs: C++
helpviewer_keywords: com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68098a5f71571931e582bc1e7be09a26fad4b8ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comptr"></a>com::ptr
Ein Wrapper für ein COM-Objekt, das als Mitglied einer CLR-Klasse verwendet werden kann. Der Wrapper automatisiert werden auch die Verwaltung der Lebensdauer der COM-Objekts, die im Besitz befindlichen Verweise auf das Objekt freigeben, wenn der Destruktor aufgerufen wird. Analog zu [von CComPtr-Klasse](../atl/reference/ccomptr-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 [com:: PTR-Klasse](../dotnet/com-ptr-class.md) wird definiert, der \<msclr\com\ptr.h > Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliothek](../dotnet/cpp-support-library.md)