---
title: SDI und MDI | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7109651bc250f83d8ee7e162b647ef54dd5308d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sdi-and-mdi"></a>SDI und MDI
MFC ist ganz einfach zum Arbeiten mit Single Document Interface (SDI) und Multiple Document Interface (MDI)-Anwendungen.  
  
 SDI-Anwendungen können nur eine offene Dokumentrahmenfenster zu einem Zeitpunkt. MDI-Anwendungen können mehrere Dokument Rahmenfenster in der gleichen Instanz einer Anwendung geöffnet sein. Eine MDI-Anwendung verfügt über ein Fenster, in welche MDI, multiple untergeordnete Fenster, die selbst Rahmenfenster sind, geöffnet werden können, mit jeweils ein separates Dokument. In einigen Anwendungen können das untergeordnete Fenster verschiedener Typen, z. B. Windows Diagramm und Tabelle Windows sein. In diesem Fall kann die Menüleiste ändern, da untergeordnete MDI-Fenster verschiedener Typen aktiviert werden.  
  
> [!NOTE]
>  Unter Windows 95 und höher, sind Anwendungen häufig SDI, da das Betriebssystem eine Ansicht "Dokument zentriert" übernommen hat.  
  
 Weitere Informationen finden Sie unter [Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
