---
title: 'MFC-ActiveX-Steuerelemente: Erweiterte Eigenschaftenimplementierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: e5357354a747dd2ce2487bf66821e8be7d2a04a4
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45534923"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC-ActiveX-Steuerelemente: Weiterführende Eigenschaftenimplementierung
Dieser Artikel beschreibt die Themen in Bezug auf die Implementierung erweiterter Eigenschaften in einem ActiveX-Steuerelement.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).  
  
-   [Schreibgeschützte und lesegeschützte Eigenschaften](#_core_read2donly_and_write2donly_properties)  
  
-   [Zurückgeben von Fehlercodes aus einer Eigenschaft](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> Schreibgeschützte und lesegeschützte Eigenschaften  
 Der Assistent zum Hinzufügen von Eigenschaften bietet eine schnelle und einfache Methode, um schreibgeschützte oder lesegeschützte Eigenschaften für das Steuerelement zu implementieren.  
  
#### <a name="to-implement-a-read-only-or-write-only-property"></a>Zum Implementieren von Schreib- oder lesegeschützte Eigenschaften  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  In der **Eigenschaftennamen** geben den Namen der Eigenschaft.  
  
6.  Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.  
  
7.  In der **Eigenschaftentyp** wählen den richtigen Typ für die Eigenschaft.  
  
8.  Wenn Sie eine schreibgeschützte Eigenschaft möchten, deaktivieren Sie den Namen der Set-Funktion. Wenn Sie eine Eigenschaft für nur-schreiben möchten, deaktivieren Sie den Namen der Get-Funktion.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
 Wenn Sie dies tun, wird der Assistent zum Hinzufügen von Eigenschaften fügt die Funktion `SetNotSupported` oder `GetNotSupported` in den Eintrag der Dispatchzuordnung anstelle einer normalen festgelegt oder Get-Funktion.  
  
 Wenn Sie eine vorhandene Eigenschaft als schreibgeschützt oder lesegeschützt ändern möchten, können Sie die Dispatchzuordnung manuell bearbeiten und entfernen Sie die unnötige Set- oder Get-Funktion von der Control-Klasse.  
  
 Wenn Sie möchten eine Eigenschaft bedingt schreibgeschützt oder lesegeschützt (z. B. nur, wenn das Steuerelement in einem bestimmten Modus ausgeführt wird), können Sie die Set- oder Get-Funktion, wie gewohnt bereitstellen und Aufrufen der `SetNotSupported` oder `GetNotSupported` funktionieren, falls zutreffend. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 In diesem Codebeispiel ruft `SetNotSupported` Wenn die `m_bReadOnlyMode` -Datenmember ist **"true"**. Wenn **"false"**, und klicken Sie dann die Eigenschaft auf den neuen Wert festgelegt ist.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> Zurückgeben von Fehlercodes aus einer Eigenschaft  
 Um anzugeben, dass ein Fehler aufgetreten ist, bei dem Versuch, eine Eigenschaft abzurufen oder festzulegen, verwenden Sie die `COleControl::ThrowError` Funktion, die einen SCODE (Statuscode:) als Parameter annimmt. Sie können einen vordefinierten SCODE oder definieren ein eigenes. Eine Liste der vordefinierten SCODEs und Anweisungen zum Definieren von benutzerdefinierten SCODEs, finden Sie unter [Behandeln von Fehlern in der ActiveX-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in Artikel ActiveX-Steuerelemente: Weiterführende Themen.  
  
 Hilfsfunktionen vorhanden sind, für die am häufigsten verwendeten SCODEs, z. B. vordefinierte [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
> [!NOTE]
>  `ThrowError` nur als Rückgabe einen Fehler aus, in einer Eigenschaft Get oder Set verwendet werden soll-Funktion oder ein Automatisierungsmethode. Hierbei handelt es sich um das einzige Mal, die der entsprechenden Ausnahmehandler übergeben werden auf dem Stapel vorhanden.  
  
 Weitere Informationen zum Melden von Ausnahmen in anderen Bereichen des Codes, finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in der ActiveX-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in diesem Artikel ActiveX-Steuerelemente: erweitert Themen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC ActiveX Controls (MFC-ActiveX-Steuerelemente)](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
