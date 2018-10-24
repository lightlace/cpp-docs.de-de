---
title: Erstellen ein Projekt für den Anbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 86f85b95b4b45624a778bc183cabadda886d002d
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990086"
---
# <a name="creating-a-project-for-the-provider"></a>Erstellen eines Projekts für den Anbieter

## <a name="to-create-a-project-in-which-the-ole-db-provider-will-reside"></a>Zum Erstellen eines Projekts, in dem der OLE DB-Anbieter befindet  
  
1. Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
1. In der **Projekttypen** Bereich, klicken Sie auf die **installiert** > **Visual C++** > **MFC/ATL** Ordner. In der **Vorlagen** Bereich, klicken Sie auf **ATL-Projekt**.  

    > [!NOTE]
    > In früheren Versionen von Visual Studio, suchen Sie den Projekttyp unter **installiert** > **Vorlagen** > **Visual C++**  >  **ATL**.
  
1. In der **Namen** , geben Sie einen Namen für das Projekt, und klicken Sie dann auf **OK**.  
  
     Die **ATL-Projektassistenten** angezeigt wird.  
  
1. In der **ATL-Projektassistenten**, wählen Sie **Dynamic Link Library (DLL)** für **Anwendungstyp**.  
  
1. Klicken Sie auf **Fertig stellen**.  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)