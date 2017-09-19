---
title: Meldungszuordnungen (MFC) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [C++], MFC
- Windows messages [C++], message maps
- messages [C++], Windows
- MFC [C++], messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bb31d35e221c9f5d06dc34408bed500b4a18b077
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="message-maps-mfc"></a>Meldungszuordnungen (MFC)
Dieser Abschnitt der Referenz Listet alle [Nachricht Zuordnungsmakros](../../mfc/reference/message-map-macros-mfc.md) und alle [CWnd](../../mfc/reference/cwnd-class.md) Meldungszuordnungseinträge zusammen mit den entsprechenden memberfunktionsprototypen:  
  
|Kategorie|Beschreibung|  
|--------------|-----------------|  
|[WM_COMMAND-Meldungshandler](../../mfc/reference/wm-command-message-handler.md)|Behandelt **WM_COMMAND** Nachrichten, die durch benutzermenüauswahlen oder Menüzugriffstasten generiert.|  
|[Untergeordnete Fenster Meldungshandler für Benachrichtigungen](../../mfc/reference/child-window-notification-message-handlers.md)|Verarbeiten Benachrichtigungen von untergeordneten Fenstern.|  
|[WM_-Meldungshandler](../../mfc/reference/handlers-for-wm-messages.md)|Behandeln **WM_** Meldungen, z. B. `WM_PAINT`.|  
|[Benutzerdefinierte Meldungshandler](../../mfc/reference/user-defined-handlers.md)|Verarbeiten benutzerdefinierte Meldungen.|  
  
 (Eine Erläuterung der Terminologie und der Konventionen, die in dieser Referenz verwendet, finden Sie unter [wie die Nachricht Querverweises](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)  
  
 Da Windows ein meldungsorientiertes Betriebssystem ist, bezieht sich ein Großteil der Programmierung für die Windows-Umgebung auf die Verarbeitung von Meldungen. Bei jeder Tastatureingabe bzw. jedem Mausklick wird eine Meldung an die Anwendung gesendet, die das Ereignis dann verarbeiten muss.  
  
 Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, das für die meldungsbasierte Programmierung optimiert wurde. In diesem Modell wird mithilfe von "Meldungszuordnungen" festgelegt, welche Funktionen die verschiedenen Meldungen für eine bestimmte Klasse verarbeiten. Meldungszuordnungen enthalten ein oder mehrere Makros, die angeben, welche Meldungen von welchen Funktionen verarbeitet werden. Eine Meldungszuordnung, die ein `ON_COMMAND`-Makro enthält, kann z. B. wie folgt aussehen:  
  
 [!code-cpp[NVC_MFCMessageMaps Nr.&16;](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]  
  
 Das `ON_COMMAND`-Makro wird zur Verarbeitung von Befehlsmeldungen verwendet, die von Menüs, Schaltflächen und Zugriffstasten generiert werden. [Makros](../../mfc/reference/message-map-macros-mfc.md) stehen zur Verfügung, um Folgendes zuzuordnen:  
  
## <a name="windows-messages"></a>Windows-Meldungen  
  
-   Steuerelementbenachrichtigungen  
  
-   Benutzerdefinierte Meldungen  
  
## <a name="command-messages"></a>Befehlsmeldungen  
  
-   Registrierte benutzerdefinierte Meldungen  
  
-   Meldungen zur Benutzeroberflächen-Aktualisierung  
  
## <a name="ranges-of-messages"></a>Meldungsbereiche  
  
-   Befehle  
  
-   Aktualisierungshandlermeldungen  
  
-   Steuerelementbenachrichtigungen  
  
 Meldungszuordnungsmakros sind zwar wichtig, Sie müssen sie im Allgemeinen jedoch nicht direkt verwenden. Dies liegt daran, dass das Eigenschaftenfenster automatisch Meldungszuordnungseinträge in den Quelldateien erstellt, wenn Sie damit Meldungsverarbeitungsfunktionen zu Meldungen zuordnen. Zum Bearbeiten oder Hinzufügen eines Meldungszuordnungseintrags können Sie jederzeit das Eigenschaftenfenster verwenden.  
  
> [!NOTE]
>  Meldungszuordnungsbereiche werden vom Eigenschaftenfenster nicht unterstützt. Sie müssen diese Meldungszuordnungseinträge selbst schreiben.  
  
 Meldungszuordnungen sind jedoch ein wichtiger Teil der Microsoft Foundation Class-Bibliothek, und Sie sollten ihre Funktionsweise kennen. Weitere Informationen finden Sie in der zur Verfügung stehenden Dokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


