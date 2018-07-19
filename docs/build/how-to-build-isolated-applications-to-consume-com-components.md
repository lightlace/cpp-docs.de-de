---
title: 'Vorgehensweise: Erstellen von isolierten Anwendungen zur COM-Komponenten | Microsoft Docs'
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
ms.openlocfilehash: 2ed2f43721eb698552ccde3e1b51ed4d6e467179
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367884"
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten
Isolierte Anwendungen sind Anwendungen, die Manifeste, die das Programm integriert haben. Sie können isolierte Anwendungen, die COM-Komponenten erstellen.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>COM-Verweise auf Manifeste von isolierten Anwendungen hinzufügen  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die isolierte Anwendung.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **Isolated COM** Eigenschaftenseite, und legen die **Datei Komponentenname** -Eigenschaft auf den Namen der COM-Komponente, die die isolierte Anwendung genutzt werden sollen.  
  
4.  Klicken Sie auf **OK**.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>Manifeste in isolierten Anwendungen integrieren  
  
1.  Öffnen Sie die Projekteigenschaftenseiten für die isolierte Anwendung.  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten, und erweitern Sie dann die **Manifesttool** Knoten.  
  
3.  Wählen Sie die **ein- und Ausgabe** Eigenschaftenseite, und legen Sie anschließend die **Manifest einbetten** -Eigenschaft gleich **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
5.  Erstellen Sie die Projektmappe.  
  
## <a name="see-also"></a>Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [Zur Seite-an-Seite-Assemblys](http://msdn.microsoft.com/library/ff951640)