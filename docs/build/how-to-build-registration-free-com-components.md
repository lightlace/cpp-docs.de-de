---
title: 'Vorgehensweise: Erstellen von registrierungsfreie COM-Komponenten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bba711f88a53a3d9b6f9eae1faed09670e95d497
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-build-registration-free-com-components"></a>Gewusst wie: Erstellen von COM-Komponenten ohne Registrierung
Registrierung von COM-Komponenten sind COM-Komponenten, die Manifeste, die die DLLs integriert haben.  
  
### <a name="to-build-manifests-into-com-components"></a>Erstellen Sie die Manifeste in COM-Komponenten  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die COM-Komponente.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen Sie anschließend die **Manifest einbetten** -Eigenschaft gleich **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## <a name="see-also"></a>Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [Zur Seite-an-Seite-Assemblys](http://msdn.microsoft.com/library/ff951640)   
 [Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)