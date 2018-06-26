---
title: 'MFC-ActiveX-Steuerelemente: Erweiterte Eigenschaftenimplementierung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2eb3ba387d4b6fcca7b30cd360dff84b9da4302a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928363"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC-ActiveX-Steuerelemente: Weiterführende Eigenschaftenimplementierung
In diesem Artikel werden Themen zur Implementierung erweiterter Eigenschaften in einem ActiveX-Steuerelement beschrieben:  
  
-   [Schreibgeschützte und lesegeschützte Eigenschaften](#_core_read2donly_and_write2donly_properties)  
  
-   [Zurückgeben von Fehlercodes aus einer Eigenschaft](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> Schreibgeschützte und lesegeschützte Eigenschaften  
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
  
##  <a name="_core_returning_error_codes_from_a_property"></a> Zurückgeben von Fehlercodes aus einer Eigenschaft  
 Um anzugeben, dass ein Fehler aufgetreten ist, bei dem Versuch, eine Eigenschaft abzurufen oder festzulegen, verwenden Sie die `COleControl::ThrowError` -Funktion, die einen SCODE (Statuscode) als Parameter akzeptiert. Sie können einen vordefinierten SCODE oder definieren ein eigenes. Eine Liste der vordefinierten SCODEs und Anweisungen zum Definieren von benutzerdefinierten SCODEs, finden Sie unter [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) in Artikel ActiveX-Steuerelemente: Weiterführende Themen.  
  
 Hilfsfunktionen vorhanden, für die am häufigsten verwendeten SCODEs, z. B. vordefinierte [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError` sollen nur als Mittel zum Zurückgeben von kein Fehlers aus einer Eigenschaft abzurufen oder festzulegen, verwendet werden-Funktion oder ein Automatisierungsmethode. Dies sind die einzigen Fälle, in denen die passenden Ausnahmehandler werden auf dem Stapel vorhanden.  
  
 Weitere Informationen zur Meldung von Ausnahmen in anderen Bereichen des Codes finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in ActiveX-Steuerelementen](../mfc/mfc-activex-controls-advanced-topics.md) Artikel ActiveX-Steuerelemente: erweitert Themen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC ActiveX Controls (MFC-ActiveX-Steuerelemente)](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
