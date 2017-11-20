---
title: 'Vorgehensweise: Erstellen von isolierten Anwendungen zur COM-Komponenten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 80fe7391f41180cb4e5a6cfed5954a8ba821f44e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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