---
title: "CTaskDialog Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CTaskDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog class"
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# CTaskDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Popupdialogfeld, das wie ein Meldungsfeld jedoch funktioniert, zusätzliche Informationen für den Benutzer angezeigt werden kann.  `CTaskDialog` enthält auch Funktionen zum Erfassen von Informationen vom Benutzer ein.  
  
## Syntax  
  
```  
class CTaskDialog : public CObject  
```  
  
## Mitglieder  
  
### Konstruktoren  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)|Erstellt ein `CTaskDialog`\-Objekt.|  
  
### Methoden  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](../Topic/CTaskDialog::AddCommandControl.md)|Fügt ein Ein Steuerelement für Befehlsschaltflächen `CTaskDialog` hinzu.|  
|[CTaskDialog::AddRadioButton](../Topic/CTaskDialog::AddRadioButton.md)|Fügt ein Optionsfeld `CTaskDialog` hinzu.|  
|[CTaskDialog::ClickCommandControl](../Topic/CTaskDialog::ClickCommandControl.md)|Ein Steuerelement für Befehlsschaltflächen Klickt ein oder eine allgemeine Schaltfläche programmgesteuert.|  
|[CTaskDialog::ClickRadioButton](../Topic/CTaskDialog::ClickRadioButton.md)|Klickt auf ein Optionsfeld programmgesteuert.|  
|[CTaskDialog::DoModal](../Topic/CTaskDialog::DoModal.md)|Zeigt das `CTaskDialog` an.|  
|[CTaskDialog::GetCommonButtonCount](../Topic/CTaskDialog::GetCommonButtonCount.md)|Ruft die Anzahl der verfügbaren allgemeinen Schaltflächen ab.|  
|[CTaskDialog::GetCommonButtonFlag](../Topic/CTaskDialog::GetCommonButtonFlag.md)|Konvertiert eine Standard\-Windows\-Schaltfläche auf das allgemeine Schaltflächentyp, der mit der `CTaskDialog`\-Klasse zugeordnet ist.|  
|[CTaskDialog::GetCommonButtonId](../Topic/CTaskDialog::GetCommonButtonId.md)|Wird einer der allgemeinen Schaltflächentypen zugeordnet `CTaskDialog` mit der Klasse zu einer Standard\-Windows\-Schaltfläche.|  
|[CTaskDialog::GetOptions](../Topic/CTaskDialog::GetOptions.md)|Gibt die Optionsflags für dieses `CTaskDialog` zurück.|  
|[CTaskDialog::GetSelectedCommandControlID](../Topic/CTaskDialog::GetSelectedCommandControlID.md)|Gibt das ausgewählte Ein Steuerelement für Befehlsschaltflächen zurück.|  
|[CTaskDialog::GetSelectedRadioButtonID](../Topic/CTaskDialog::GetSelectedRadioButtonID.md)|Gibt das Optionsfeld aktiviert zurück.|  
|[CTaskDialog::GetVerificationCheckboxState](../Topic/CTaskDialog::GetVerificationCheckboxState.md)|Ruft den Zustand des Überprüfungskontrollkästchens ab.|  
|[CTaskDialog::IsCommandControlEnabled](../Topic/CTaskDialog::IsCommandControlEnabled.md)|Bestimmt, ob ein Ein Steuerelement für Befehlsschaltflächen oder eine allgemeine Schaltfläche aktiviert ist.|  
|[CTaskDialog::IsRadioButtonEnabled](../Topic/CTaskDialog::IsRadioButtonEnabled.md)|Bestimmt, ob ein Optionsfeld aktiviert ist.|  
|[CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md)|Bestimmt, ob der Computer, auf dem die Anwendung ausgeführt wird, `CTaskDialog` unterstützt.|  
|[CTaskDialog::LoadCommandControls](../Topic/CTaskDialog::LoadCommandControls.md)|Fügt Befehlsschaltflächensteuerelemente mithilfe von Daten aus der Zeichenfolgentabelle hinzu.|  
|[CTaskDialog::LoadRadioButtons](../Topic/CTaskDialog::LoadRadioButtons.md)|Fügt Optionsfelder mithilfe von Daten aus der Zeichenfolgentabelle hinzu.|  
|[CTaskDialog::NavigateTo](../Topic/CTaskDialog::NavigateTo.md)|Überträgt den Fokus zu einem anderen `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](../Topic/CTaskDialog::OnCommandControlClick.md)|Das Framework ruft diese Methode auf, wenn der Benutzer auf ein Ein Steuerelement für Befehlsschaltflächen klickt.|  
|[CTaskDialog::OnCreate](../Topic/CTaskDialog::OnCreate.md)|Das Framework ruft diese Methode auf, nachdem es `CTaskDialog` erstellt.|  
|[CTaskDialog::OnDestroy](../Topic/CTaskDialog::OnDestroy.md)|Das Framework ruft diese Methode auf, unmittelbar vor dem `CTaskDialog` zerstört.|  
|[CTaskDialog::OnExpandButtonClick](../Topic/CTaskDialog::OnExpandButtonClick.md)|Das Framework ruft diese Methode auf, wenn der Benutzer auf der Erweiterungsschaltfläche klickt.|  
|[CTaskDialog::OnHelp](../Topic/CTaskDialog::OnHelp.md)|Das Framework ruft diese Methode auf, wenn die Benutzeranforderungen unterstützen.|  
|[CTaskDialog::OnHyperlinkClick](../Topic/CTaskDialog::OnHyperlinkClick.md)|Das Framework ruft diese Methode auf, wenn der Benutzer auf einen Link klickt.|  
|[CTaskDialog::OnInit](../Topic/CTaskDialog::OnInit.md)|Das Framework ruft diese Methode auf, wenn `CTaskDialog` initialisiert wird.|  
|[CTaskDialog::OnNavigatePage](../Topic/CTaskDialog::OnNavigatePage.md)|Das Framework ruft diese Methode auf, wenn der Benutzer den Fokus hinsichtlich der Steuerelemente auf `CTaskDialog` verschoben wird.|  
|[CTaskDialog::OnRadioButtonClick](../Topic/CTaskDialog::OnRadioButtonClick.md)|Das Framework ruft diese Methode auf, wenn der Benutzer ein Optionsfeld\-Steuerelement auswählt.|  
|[CTaskDialog::OnTimer](../Topic/CTaskDialog::OnTimer.md)|Das Framework ruft diese Methode auf, wenn der Zeitgeber abläuft.|  
|[CTaskDialog::OnVerificationCheckboxClick](../Topic/CTaskDialog::OnVerificationCheckboxClick.md)|Das Framework ruft diese Methode auf, wenn der Benutzer auf das Überprüfungskontrollkästchen klickt.|  
|[CTaskDialog::RemoveAllCommandControls](../Topic/CTaskDialog::RemoveAllCommandControls.md)|Entfernt alle Befehlssteuerelemente von `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](../Topic/CTaskDialog::RemoveAllRadioButtons.md)|Entfernt alle Optionsfelder von `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](../Topic/CTaskDialog::SetCommandControlOptions.md)|Aktualisiert ein Ein Steuerelement für Befehlsschaltflächen auf `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](../Topic/CTaskDialog::SetCommonButtonOptions.md)|Aktualisiert eine Teilmenge allgemeine aktiviert werden, Schaltflächen und erfordert UAC\-Ausweitung.|  
|[CTaskDialog::SetCommonButtons](../Topic/CTaskDialog::SetCommonButtons.md)|Fügt allgemeine Schaltflächen `CTaskDialog` hinzu.|  
|[CTaskDialog::SetContent](../Topic/CTaskDialog::SetContent.md)|Aktualisiert den Inhalt `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](../Topic/CTaskDialog::SetDefaultCommandControl.md)|Gibt das standardmäßige Ein Steuerelement für Befehlsschaltflächen an.|  
|[CTaskDialog::SetDefaultRadioButton](../Topic/CTaskDialog::SetDefaultRadioButton.md)|Gibt das standardmäßige Optionsfeld an.|  
|[CTaskDialog::SetDialogWidth](../Topic/CTaskDialog::SetDialogWidth.md)|Passt die Breite `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](../Topic/CTaskDialog::SetExpansionArea.md)|Aktualisiert den Erweiterungsbereich `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](../Topic/CTaskDialog::SetFooterIcon.md)|Aktualisiert das Fußzeilensymbol für `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](../Topic/CTaskDialog::SetFooterText.md)|Aktualisiert den Text in der Fußzeile `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](../Topic/CTaskDialog::SetMainIcon.md)|Aktualisiert das Symbol `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](../Topic/CTaskDialog::SetMainInstruction.md)|Aktualisiert die Anweisung `CTaskDialog`.|  
|[CTaskDialog::SetOptions](../Topic/CTaskDialog::SetOptions.md)|Konfiguriert die Optionen für `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](../Topic/CTaskDialog::SetProgressBarMarquee.md)|Konfiguriert eine Laufschriftleiste für `CTaskDialog` und fügt sie dem Dialogfeld hinzu.|  
|[CTaskDialog::SetProgressBarPosition](../Topic/CTaskDialog::SetProgressBarPosition.md)|Passt die Position der Statusanzeige.|  
|[CTaskDialog::SetProgressBarRange](../Topic/CTaskDialog::SetProgressBarRange.md)|Passt den Bereich der Statusanzeige.|  
|[CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md)|Legt den Zustand der Statusanzeige fest und zeigt diesen auf `CTaskDialog` an.|  
|[CTaskDialog::SetRadioButtonOptions](../Topic/CTaskDialog::SetRadioButtonOptions.md)|Aktiviert oder deaktiviert ein Optionsfeld.|  
|[CTaskDialog::SetVerificationCheckbox](../Topic/CTaskDialog::SetVerificationCheckbox.md)|Legt den aktivierten Zustand des Überprüfungskontrollkästchens fest.|  
|[CTaskDialog::SetVerificationCheckboxText](../Topic/CTaskDialog::SetVerificationCheckboxText.md)|Legt den Text auf der rechten Seite des Überprüfungskontrollkästchens fest.|  
|[CTaskDialog::SetWindowTitle](../Topic/CTaskDialog::SetWindowTitle.md)|Legt den Titel `CTaskDialog` fest.|  
|[CTaskDialog::ShowDialog](../Topic/CTaskDialog::ShowDialog.md)|Erstellt und zeigt `CTaskDialog` an.|  
|[CTaskDialog::TaskDialogCallback](../Topic/CTaskDialog::TaskDialogCallback.md)|Das Framework ruft dieses als Reaktion auf verschiedene Windows\-Meldungen auf.|  
  
### Datenmember  
  
|||  
|-|-|  
|`m_aButtons`|Das Array von Befehlsschaltflächensteuerelementen für `CTaskDialog`.|  
|`m_aRadioButtons`|Das Array von Optionsfeld\-Steuerelementen für `CTaskDialog`.|  
|`m_bVerified`|`TRUE` gibt das Überprüfungskontrollkästchen wird überprüft an; `FALSE` gibt es ist nicht an.|  
|`m_footerIcon`|Das Symbol in der Fußzeile `CTaskDialog`.|  
|`m_hWnd`|Ein Handle für das Fenster für `CTaskDialog`.|  
|`m_mainIcon`|Das hauptsächliche Symbol `CTaskDialog`.|  
|`m_nButtonDisabled`|Eine Maske, die angibt, die aus allgemeinen Schaltflächen deaktiviert werden.|  
|`m_nButtonElevation`|Eine Maske, die angibt, die aus allgemeinen Schaltflächen UAC\-Ausweitung erfordern.|  
|`m_nButtonId`|Die ID des ausgewählten Befehlsschaltflächensteuerelements.|  
|`m_nCommonButton`|Eine Maske, die angibt, das allgemeine Schaltflächen auf `CTaskDialog` angezeigt werden.|  
|`m_nDefaultCommandControl`|Die ID des Befehlsschaltflächensteuerelements, das ausgewählt wird, wenn `CTaskDialog` angezeigt wird.|  
|`m_nDefaultRadioButton`|Die ID des RadioButton\-Steuerelements, das ausgewählt wird, wenn `CTaskDialog` angezeigt wird.|  
|`m_nFlags`|Eine Maske, die die Optionen für `CTaskDialog` angibt.|  
|`m_nProgressPos`|Die aktuelle Position der Statusanzeige.  Dabei muss es sich um einen Wert zwischen `m_nProgressRangeMin` und `m_nProgressRangeMax` handeln.|  
|`m_nProgressRangeMax`|Der maximale Wert für die Statusanzeige.|  
|`m_nProgressRangeMin`|Der minimale Wert für die Statusanzeige.|  
|`m_nProgressState`|Der Zustand der Statusanzeige.  Weitere Informationen finden Sie unter [CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md).|  
|`m_nRadioId`|Die ID des Steuerelements des aktivierten Optionsfelds.|  
|`m_nWidth`|Die Breite des `CTaskDialog` in Pixel.|  
|`m_strCollapse`|Die Zeichenfolge, die `CTaskDialog` auf der rechten Seite des Erweiterungsfelds anzeigt, wenn die erweiterten Informationen ausgeblendet werden.|  
|`m_strContent`|Die Zeichenfolge `CTaskDialog`.|  
|`m_strExpand`|Die Zeichenfolge, die `CTaskDialog` auf der rechten Seite des Erweiterungsfelds anzeigt, wenn die erweiterten Informationen angezeigt werden.|  
|`m_strFooter`|Die Fußzeile `CTaskDialog`.|  
|`m_strInformation`|Die erweiterten Informationen für `CTaskDialog`.|  
|`m_strMainInstruction`|Die Anweisung `CTaskDialog`.|  
|`m_strTitle`|Der Titel der `CTaskDialog`.|  
|`m_strVerification`|Die Zeichenfolge, die `CTaskDialog` auf der rechten Seite des Überprüfungskontrollkästchens anzeigt.|  
  
## Hinweise  
 Die `CTaskDialog`\-Klasse ersetzt das Standardwindows\-meldungs\-Feld und verfügt über zusätzliche Funktionen wie neue Steuerelemente, mit der Informationen vom Benutzer zu erfassen.  Diese Klasse ist in der MFC\-Bibliothek in [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  `CTaskDialog` ist verfügbar Starten mit [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  In früheren Versionen von Windows können das `CTaskDialog`\-Objekt nicht anzeigen.  Verwenden Sie `CTaskDialog::IsSupported`, um zur Laufzeit zu bestimmen, ob der aktuelle Benutzer das Aufgabendialogfeld anzeigen kann.  Das Standardwindows\-meldungs\-Feld wird weiterhin in [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)] unterstützt.  
  
 `CTaskDialog` ist nur verfügbar, wenn Sie die Anwendung erstellen, indem Sie die Unicode\-Bibliothek verwenden.  
  
 `CTaskDialog` verfügt über zwei verschiedene Konstruktoren.  Ein Konstruktor ermöglicht es Ihnen, zwei Befehlsschaltflächen und maximal sechs regulären Schaltflächen\-Steuerelemente anzugeben.  Sie können mehr Befehlsschaltflächen hinzufügen, nachdem Sie `CTaskDialog` erstellen.  Der zweite Konstruktor unterstützt keine Befehlsschaltflächen, aber Sie können eine unbegrenzte Anzahl reguläre Schaltflächen\-Steuerelemente hinzufügen.  Weitere Informationen über die Konstruktoren, finden Sie unter [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md).  
  
 Im folgenden Bild wird ein Beispiel `CTaskDialog` an, um den Speicherort von einigen der Steuerelemente zu veranschaulichen.  
  
 ![Beispiel für CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialogSample")  
CTaskDialog\-Beispiel  
  
## Anforderungen  
 **Minimales erforderliches Betriebssystem:** [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **Header:** afxtaskdialog.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Exemplarische Vorgehensweise: Hinzufügen eines CTaskDialog zu einer Anwendung](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)