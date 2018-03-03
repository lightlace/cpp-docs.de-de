---
title: 'MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers | Microsoft Docs'
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
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c3de04fbbfa9f2d0b55b7e31ca02faeddfa5c12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers
Sie können ein MFC-ActiveX-Steuerelement als Automatisierungsserver programmgesteuert Einbetten des Steuerelements in einer anderen Anwendung und das Aufrufen von Methoden im Steuerelement aus der Anwendung entwickeln. Z. B. ein Steuerelement würde in einem ActiveX-Steuerelementcontainer gehostet werden weiterhin zur Verfügung.  
  
### <a name="to-create-a-control-as-an-automation-server"></a>So erstellen Sie ein Steuerelement als Automatisierungsserver  
  
1.  [Erstellen Sie](../mfc/reference/mfc-activex-control-wizard.md) des Steuerelements.  
  
2.  [Hinzufügen von Methoden](../mfc/mfc-activex-controls-methods.md).  
  
3.  Überschreiben Sie [Sie IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed). Weitere Informationen finden Sie im Knowledge Base-Artikel Q146120.  
  
4.  Erstellen Sie das Steuerelement.  
  
### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Die Methoden in eines Automatisierungsservers programmgesteuerten Zugriff auf  
  
1.  Erstellen Sie z. B. eine Anwendung, ein [MFC Exe](../mfc/reference/mfc-application-wizard.md).  
  
2.  Am Anfang der `InitInstance` -Funktion, fügen Sie die folgende Zeile hinzu:  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  In der Klassenansicht mit der rechten Maustaste des Projektknotens, und wählen Sie **Hinzufügen von Klassen aus der Typbibliothek** zum Importieren der Typbibliothek.  
  
     Dadurch wird dem Projekt Dateien mit der Datei Namen Erweiterungen h "und" Class1.cpp hinzugefügt.  
  
4.  In der Headerdatei der Klasse, in denen rufen Sie eine oder mehrere Methoden in der ActiveX-Steuerelement, fügen Sie die folgende Zeile: `#include filename.h`, wobei Dateiname den Namen der Headerdatei, die beim Importieren der Typbibliothek erstellt wurde.  
  
5.  Fügen Sie in der Funktion an eine Methode in das ActiveX-Steuerelement, in dem kein Anruf ausgeführt wird Code, der ein Objekt, das Steuerelement-Wrapperklasse erstellt, und erstellen Sie das ActiveX-Objekt. Beispielsweise instanziiert der folgende MFC-Code eine `CCirc` -Steuerelement, ruft die Beschriftung-Eigenschaft ab, und das Ergebnis wird angezeigt, wenn in einem Dialogfeld die Schaltfläche "OK" geklickt wird:  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 Wenn Sie nach der Verwendung in einer Anwendung Methoden das ActiveX-Steuerelement hinzufügen, können Sie beginnen, verwenden die neueste Version des Steuerelements in der Anwendung durch Löschen der Dateien, die beim Importieren der Typbibliothek erstellt wurden. Importieren der Typbibliothek dann erneut.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

