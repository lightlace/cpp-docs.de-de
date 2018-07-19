---
title: 'com:: PTR | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr
dev_langs:
- C++
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f3c4e3bb91e161f9176bcf6964fc843d4e4bd707
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104525"
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