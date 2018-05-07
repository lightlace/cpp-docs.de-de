---
title: 'TN032: MFC-Ausnahmemechanismus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5256f787534ab408920f7154122ae0c5934019c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC-Ausnahmemechanismus
Standard C++-Ausnahmemechanismus wurde von frühere Versionen von Visual C++ nicht unterstützt und MFC bereitgestellten Makros **TRY/CATCH/THROW** stattdessen verwendet wurden. C++-Ausnahmen werden von dieser Version von Visual C++ vollständig unterstützt. Dieser Hinweis behandelt einige der erweiterten Implementierungsdetails der vorherigen Makros auch das automatisch Cleanup Stapel basierte Objekte. Da C++-Ausnahmen stapelentladung standardmäßig unterstützen, ist dieser technischen Hinweis nicht mehr erforderlich.  
  
 Verweisen auf [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) für Weitere Informationen zu den Unterschieden zwischen den MFC-Makros und die neuen C++-Schlüsselwörter.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

