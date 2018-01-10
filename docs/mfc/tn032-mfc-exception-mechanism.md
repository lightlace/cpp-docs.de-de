---
title: 'TN032: MFC-Ausnahmemechanismus | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.exceptions
dev_langs: C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf82d4b158cedd2d8f6916dfb01d26db6c62d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC-Ausnahmemechanismus
Standard C++-Ausnahmemechanismus wurde von frühere Versionen von Visual C++ nicht unterstützt und MFC bereitgestellten Makros **TRY/CATCH/THROW** stattdessen verwendet wurden. C++-Ausnahmen werden von dieser Version von Visual C++ vollständig unterstützt. Dieser Hinweis behandelt einige der erweiterten Implementierungsdetails der vorherigen Makros auch das automatisch Cleanup Stapel basierte Objekte. Da C++-Ausnahmen stapelentladung standardmäßig unterstützen, ist dieser technischen Hinweis nicht mehr erforderlich.  
  
 Verweisen auf [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) für Weitere Informationen zu den Unterschieden zwischen den MFC-Makros und die neuen C++-Schlüsselwörter.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

