---
title: 'Vorgehensweise: Erstellen von isolierten Anwendungen zur COM-Komponenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b94a41aef1122a507a8966c475b9a87c69e3789
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196831"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten
Isolierte Anwendungen sind Anwendungen, die Manifeste, die die Anwendung integriert haben. Sie können die isolierte Anwendungen zur COM-Komponenten erstellen.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>COM-Verweise auf die Manifeste der isolierten Anwendungen hinzufügen  
  
1.  Öffnen Sie die Eigenschaftenseiten des Projekts für die isolierte Anwendung.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **Isolated COM** Eigenschaftenseite, und legen anschließend die **Komponentendateiname** -Eigenschaft auf den Namen der COM-Komponente, die Sie auf die isolierte Anwendung nutzen möchten.  
  
4.  Klicken Sie auf **OK**.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>Manifeste in isolierten Anwendungen zu integrieren.  
  
1.  Öffnen Sie die Eigenschaftenseiten des Projekts für die isolierte Anwendung.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen anschließend die **Manifest einbetten** -Eigenschaft **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## <a name="see-also"></a>Siehe auch  
 [Isolated Applications (Isolierte Anwendungen)](/windows/desktop/SbsCs/isolated-applications)   
 [Zu Seite-an-Seite-Assemblys](/windows/desktop/SbsCs/about-side-by-side-assemblies-)