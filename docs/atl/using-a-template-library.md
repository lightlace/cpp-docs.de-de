---
title: Mit einem Template Library (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- template libraries
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5232d2169ae9442a945b48ba141a609003611a90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-template-library"></a>Verwenden einer Vorlagenbibliothek
Eine Vorlage ähnelt einem Makro. Wie bei einem Makro, bewirkt, dass eine Vorlage aufrufen (mit entsprechenden Vorlagenparameter) erweitern in dem von Ihnen geschriebenen Code. Geht jedoch eine Vorlage für weitere ermöglichen die Erstellung neuer Klassen, die basierend auf Typen, die Sie als Parameter übergeben. Diese neue Klassen implementieren als typsicherer Methoden zum Ausführen des Vorgangs im Vorlagencode ausgedrückt.  
  
 Vorlagenbibliotheken wie ATL herkömmliche C++-Klassenbibliotheken unterscheiden sich insofern, dass sie in der Regel nur als Quellcode (oder als Quellcode mit ein wenig, zur Laufzeit unterstützen) bereitgestellt werden und sind nicht grundsätzlich oder unbedingt hierarchisch. Anstatt das Ableiten einer Klasse, die Funktionalität zu erhalten, die Sie wünschen, instanziieren Sie eine Klasse aus einer Vorlage.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in ATL](../atl/introduction-to-atl.md)

