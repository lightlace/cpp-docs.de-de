---
title: SDI und MDI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db63efe8d7e2622610bb56f5e6885b72b705093b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sdi-and-mdi"></a>SDI und MDI
MFC ist ganz einfach zum Arbeiten mit Single Document Interface (SDI) und Multiple Document Interface (MDI)-Anwendungen.  
  
 SDI-Anwendungen können nur eine offene Dokumentrahmenfenster zu einem Zeitpunkt. MDI-Anwendungen können mehrere Dokument Rahmenfenster in der gleichen Instanz einer Anwendung geöffnet sein. Eine MDI-Anwendung verfügt über ein Fenster, in welche MDI, multiple untergeordnete Fenster, die selbst Rahmenfenster sind, geöffnet werden können, mit jeweils ein separates Dokument. In einigen Anwendungen können das untergeordnete Fenster verschiedener Typen, z. B. Windows Diagramm und Tabelle Windows sein. In diesem Fall kann die Menüleiste ändern, da untergeordnete MDI-Fenster verschiedener Typen aktiviert werden.  
  
> [!NOTE]
>  Unter Windows 95 und höher, sind Anwendungen häufig SDI, da das Betriebssystem eine Ansicht "Dokument zentriert" übernommen hat.  
  
 Weitere Informationen finden Sie unter [Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
