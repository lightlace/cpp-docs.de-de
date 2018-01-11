---
title: 'MFC-ActiveX-Steuerelemente: Methoden | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e3b343b13118930612e4adfed4c33a65a9e7be8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-methods"></a>MFC-ActiveX-Steuerelemente: Methoden
Ein ActiveX-Steuerelement löst Ereignisse für die Kommunikation zwischen sich selbst und seine Steuerelementcontainer. Ein Container kann auch mithilfe von Methoden und Eigenschaften mit einem Steuerelement kommunizieren. Methoden werden auch als Funktionen bezeichnet.  
  
 Methoden und Eigenschaften geben Sie eine exportierte Schnittstelle für die Verwendung durch andere Anwendungen, z. B. Automatisierungsclients und ActiveX-Steuerelementcontainer. Weitere Informationen zu Eigenschaften von ActiveX-Steuerelements, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md).  
  
 Methoden ähneln sich Zweck und die Memberfunktionen einer C++-Klasse. Es gibt zwei Arten von Methoden, die das Steuerelement implementieren kann: vordefinierte und benutzerdefinierte. Ähnlich wie für vordefinierte Ereignisse SKU-Methoden sind Methoden für die [COleControl](../mfc/reference/colecontrol-class.md) stellt eine Implementierung bereit. Weitere Informationen über vordefinierte Methoden finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen der Stock-Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md). Benutzerdefinierte Methoden, die vom Entwickler definierten ermöglichen die weitere Anpassung des Steuerelements. Weitere Informationen finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md).  
  
 Die Microsoft Foundation Class-Bibliothek (MFC) implementiert einen Mechanismus, der das Steuerelement auf vordefinierte und benutzerdefinierte Methoden unterstützen kann. Der erste Teil ist die Klasse `COleControl`. Abgeleitet von `CWnd`, `COleControl` Memberfunktionen unterstützen stock-Methoden, die für alle ActiveX-Steuerelemente gelten. Der zweite Teil dieses Mechanismus ist die Dispatchzuordnung. Eine Dispatchzuordnung ähnelt einer meldungszuordnung; anstatt eine Windows-Nachrichten-ID eine Funktion zuordnen, ordnet eine Dispatchzuordnung virtuelle Memberfunktionen IDispatch-IDs.  
  
 Für ein Steuerelement verschiedene Methoden ordnungsgemäß unterstützt muss ihre Klasse eine Dispatchzuordnung deklarieren. Dies wird erreicht, indem die folgende Codezeile befindet sich im Header der Control-Klasse (. H)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]  
  
 Die Hauptaufgabe der Dispatchzuordnung ist die Beziehung zwischen den Methodennamen, der von einem externen Aufrufer (z. B. den Container) und die Memberfunktionen der Klasse des Steuerelements, die die Methoden implementieren verwendet herstellen. Nachdem die Dispatchzuordnung deklariert wurde, muss er in der Implementierung des Steuerelements definiert werden (. CPP)-Datei. Die folgenden Codezeilen definieren die Dispatchzuordnung:  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]  
  
 Bei Verwendung der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md) um das Projekt zu erstellen, diese Zeilen automatisch hinzugefügt wurden. Wenn die MFC-ActiveX-Steuerelement-Assistent nicht verwendet wurde, müssen Sie die folgenden Zeilen manuell hinzufügen.  
  
 In den folgenden Artikeln werden die Methoden im Detail beschrieben:  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

