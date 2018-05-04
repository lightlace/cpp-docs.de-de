---
title: Angeben der Threadingmodell für ein Projekt (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f807aa82a62fb703430ace5bc6be516e08ca9dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Angeben des Threadingmodells für ein Projekt (ATL)
Die folgenden Makros sind zum Angeben des Threadingmodells der ATL-Projekt verfügbar:  
  
|Makro|Richtlinien für die Verwendung|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|Definieren Sie, wenn alle Objekte der einzelne Threadingmodell verwenden.|  
|_ATL_APARTMENT_THREADED|Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.|  
|_ATL_FREE_THREADED|Definieren Sie, wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden. Vorhandener Code möglicherweise Verweise auf das entsprechende Makro [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|  
  
 Wenn Sie diese Makros nicht für das Projekt definieren, werden die _ATL_FREE_THREADED wirksam.  
  
 Die Makros beeinflussen die Leistung zur Laufzeit wie folgt:  
  
-   Das Makro, das die Objekte in Ihrem Projekt entspricht, angeben, kann zur Laufzeit-Leistung verbessern.  
  
-   Angeben einer höheren Ebene Makros, z. B. Wenn Sie _ATL_APARTMENT_THREADED angeben, wenn alle Objekte einzelne werden verkettet, wird etwas laufzeitleistung beeinträchtigt werden.  
  
-   Angeben einer niedrigeren Ebene Makros, z. B., wenn Sie angeben, dass _ATL_SINGLE_THREADED, wenn mindestens ein oder mehrere der Objekte können Sie Apartmentthreading oder Freethreadings, kann dazu führen, dass die Anwendung zur Laufzeit fehlschlagen.  
  
 Finden Sie unter [Optionen, ATL-Assistent für einfache Objekte](../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modelle für eine ATL-Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)

