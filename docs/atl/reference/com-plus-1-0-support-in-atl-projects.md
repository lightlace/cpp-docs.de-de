---
title: COM+ 1.0-Unterstützung in ATL-Projekte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3440d3ed2e3244b35588d5c07fd181f1ad2f082
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="com-10-support-in-atl-projects"></a>COM+ 1.0-Unterstützung in ATL-Projekte
Sie können die [ATL-Projekt-Assistent](../../atl/reference/creating-an-atl-project.md) zum Erstellen eines Projekts mit grundlegende Unterstützung für COM+ 1.0-Komponenten.  
  
 COM+ 1.0 wurde für verteilte Anwendungen mit komponentenbasierter Entwicklung entwickelt. Darüber hinaus eine Laufzeitinfrastruktur zum Bereitstellen und verwalten diese Anwendungen.  
  
 Bei Auswahl der **COM+ 1.0-Unterstützung** Kontrollkästchen, die der Assistent ändert das Buildskript im Linkschritt. Insbesondere das COM+ 1.0-Projektlinks zu den folgenden Bibliotheken:  
  
-   comsvcs.lib hinzu:  
  
-   Mtxguid.lib  
  
 Bei Auswahl der **COM+ 1.0-Unterstützung** , Sie können auch Kontrollkästchen **Unterstützung Komponente Registrierungsstelle**. Die Registrierung der Komponente ermöglicht das COM+ 1.0-Objekt zum Abrufen einer Liste der Komponenten, Komponenten registrieren oder Aufheben der Registrierung Komponenten (einzeln oder alle auf einmal).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

