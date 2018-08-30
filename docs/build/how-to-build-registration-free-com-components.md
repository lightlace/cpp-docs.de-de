---
title: 'Vorgehensweise: Erstellen von registrierungsfreie COM-Komponenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eaf9417f4d2b3b825933589556055772b84e057
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197412"
---
# <a name="how-to-build-registration-free-com-components"></a>Gewusst wie: Erstellen von COM-Komponenten ohne Registrierung
COM-Komponenten ohne Registrierung sind COM-Komponenten, die Manifeste, die die DLLs integriert haben.  
  
### <a name="to-build-manifests-into-com-components"></a>Erstellen von Manifesten in COM-Komponenten  
  
1.  Öffnen Sie die Eigenschaftenseiten des Projekts für die COM-Komponente.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen anschließend die **Manifest einbetten** -Eigenschaft **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## <a name="see-also"></a>Siehe auch  
 [Isolated Applications (Isolierte Anwendungen)](/windows/desktop/SbsCs/isolated-applications)   
 [Zu Seite-an-Seite-Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-)   
 [Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)