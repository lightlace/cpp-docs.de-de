---
title: 'Vorgehensweise: Erstellen von registrierungsfreie COM-Komponenten | Microsoft Docs'
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
ms.openlocfilehash: e54327344d61cc70e68b528c5f88f3d30f5d185a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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