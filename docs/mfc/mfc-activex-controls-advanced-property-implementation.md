---
title: 'MFC-ActiveX-Steuerelemente: Erweiterte Eigenschaftenimplementierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ac8b2cb1a9c8de43ecfbd2f4712d19750bb143a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC-ActiveX-Steuerelemente: Weiterführende Eigenschaftenimplementierung
In diesem Artikel werden Themen zur Implementierung erweiterter Eigenschaften in einem ActiveX-Steuerelement beschrieben:  
  
-   [Schreibgeschützte und lesegeschützte Eigenschaften](#_core_read2donly_and_write2donly_properties)  
  
-   [Zurückgeben von Fehlercodes aus einer Eigenschaft](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a>Schreibgeschützte und lesegeschützte Eigenschaften  
 Der Assistent zum Hinzufügen von Eigenschaften bietet eine schnelle und einfache Methode, um nur-Lese oder nur-schreiben Eigenschaften für das Steuerelement zu implementieren.  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>Um eine nur-Lese oder nur-Schreiben Eigenschaft zu implementieren.  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  In der **Eigenschaftsname** geben den Namen der Eigenschaft.  
  
6.  Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.  
  
7.  In der **Eigenschaftentyp** Feld, wählen Sie den richtigen Typ für die Eigenschaft.  
  
8.  Wenn Sie eine schreibgeschützte Eigenschaft soll, deaktivieren Sie Name der Funktion. Wenn Sie eine Nur-Schreiben Eigenschaft soll, deaktivieren Sie den Namen der Get-Funktion.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
 Wenn Sie dies tun, wird der Assistent zum Hinzufügen von Eigenschaften fügt die Funktion `SetNotSupported` oder `GetNotSupported` legen Sie den Eintrag der Dispatchzuordnung anstelle einer normalen oder Get-Funktion.  
  
 Wenn Sie eine vorhandene Eigenschaft als schreibgeschützt oder lesegeschützt ändern möchten, können Sie die Dispatchzuordnung manuell bearbeiten und entfernen Sie die unnötige Set- oder Get-Funktion von der Control-Klasse.  
  
 Wenn eine Eigenschaft bedingt schreibgeschützt oder lesegeschützt (z. B. nur, wenn das Steuerelement in einem bestimmten Modus betrieben wird) werden soll, können Sie das Set- oder Get-Funktion wie gewohnt angeben und Aufrufen der `SetNotSupported` oder `GetNotSupported` funktionieren, falls zutreffend. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 In diesem Codebeispiel ruft `SetNotSupported` Wenn die `m_bReadOnlyMode` -Datenmember ist **"true"**. Wenn **"false"**, und klicken Sie dann die Eigenschaft auf den neuen Wert festgelegt ist.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a>Zurückgeben von Fehlercodes aus einer Eigenschaft  
 Um anzugeben, dass ein Fehler aufgetreten ist, bei dem Versuch, eine Eigenschaft abzurufen oder festzulegen, verwenden Sie die `COleControl::ThrowError` -Funktion, die akzeptiert ein `SCODE` (Statuscode) als Parameter. Sie können eine vordefinierte `SCODE` oder ein eigenes definieren. Eine Liste der vordefinierten `SCODE`s sowie Anweisungen zum Definieren von benutzerdefinierten `SCODE`s, finden Sie unter [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in Artikel ActiveX-Steuerelemente: Weiterführende Themen.  
  
 Hilfsfunktionen für die am häufigsten verwendeten vordefinierten vorhanden `SCODE`s, z. B. [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError`sollen nur als Mittel zum Zurückgeben von kein Fehlers aus einer Eigenschaft abzurufen oder festzulegen, verwendet werden-Funktion oder ein Automatisierungsmethode. Dies sind die einzigen Fälle, in denen die passenden Ausnahmehandler werden auf dem Stapel vorhanden.  
  
 Weitere Informationen zur Meldung von Ausnahmen in anderen Bereichen des Codes finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) Artikel ActiveX-Steuerelemente: erweitert Themen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
