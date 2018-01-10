---
title: Erstellen des Anbieters | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6e590461d359c2ab2ee750f0393f6c2f9ec7ac95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-provider"></a>Erstellen des Anbieters
#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>So erstellen Sie einen OLE DB-Anbieter mit der ATL-OLE DB-Anbieter-Assistenten  
  
1.  Mit der rechten Maustaste in des Projekts.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  In der **Klasse hinzufügen** wählen Sie im Dialogfeld die **ATL-OLE DB-Anbieter** Symbol, und klicken Sie dann auf **öffnen**.  
  
4.  In der ATL-OLE DB-Anbieter-Assistenten geben Sie einen kurzen Namen für den Anbieter in der **Kurzname** Feld. In den folgenden Themen der kurzen Name "MyProvider", jedoch können Sie einen anderen Namen. Die anderen Namensfeldern entsprechend den Namen, den Sie eingeben.  
  
5.  Bearbeiten Sie die anderen Namensfelder, bei Bedarf. Zusätzlich zu dem Objekt und die Dateinamen können Sie die folgenden bearbeiten:  
  
    -   **Co-Klasse**: der Name, die COM verwendet, um den Anbieter zu erstellen.  
  
    -   **ProgID**: der programmgesteuerte Bezeichner, also eine Textzeichenfolge, die anstelle einer GUID verwendet werden kann.  
  
    -   **Version**: mit ProgID "und" Co-Klasse verwendet, um eine programmgesteuerte versionsabhängige-ID zu generieren.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)