---
title: VCPROFILE_ALLOC_SCALE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VCPROFILE_ALLOC_SCALE
dev_langs: C++
helpviewer_keywords: VCPROFILE_ALLOC_SCALE environment variable
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed767299778b65a7275bbfd225daaf46ec0e98be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE
Ändern Sie die Speichermenge belegt werden, um die Profildaten enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### <a name="parameters"></a>Parameter  
 `scale_value`  
 Der Wert für die Dezimalstellen für die Menge an Arbeitsspeicher zum Ausführen des Testszenarios werden sollen.  Der Standard ist 1.  
  
## <a name="remarks"></a>Hinweise  
 In seltenen Fällen kann es werden genügend Arbeitsspeicher zur Unterstützung beim Ausführen des Testszenarios Profil Datensammlung.  In diesen Fällen können Sie erhöhen die Größe des Arbeitsspeichers mit `VCPROFILE_ALLOC_SCALE`.  
  
 Wenn Sie während eines Testlaufs eine Fehlermeldung, der angibt erhalten, dass Sie nicht genügend Arbeitsspeicher verfügen, weisen Sie einen höheren Wert zu `VCPROFILE_ALLOC_SCALE`, bis der Test abgeschlossen, ohne Out-of-Memory-Fehler ausgeführt wird.  
  
## <a name="example"></a>Beispiel  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)