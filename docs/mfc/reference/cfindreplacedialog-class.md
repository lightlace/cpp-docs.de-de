---
title: "CFindReplaceDialog Class"
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
  - "CFindReplaceDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFindReplaceDialog class"
  - "Find/Replace dialog box"
  - "Ersetzen von Text"
  - "Ersetzen von Text, CFindReplaceDialog class"
  - "Textsuche, CFindReplaceDialog class"
  - "Textsuche, Ersetzen von Text"
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
caps.latest.revision: 25
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CFindReplaceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht, Sie zu Werkzeugstandardzeichenfolge Suchen\/ersetzt Dialogfelder in der Anwendung.  
  
## Syntax  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](../Topic/CFindReplaceDialog::CFindReplaceDialog.md)|Rufen Sie diese Funktion auf, um ein `CFindReplaceDialog`\-Objekt zu erstellen.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](../Topic/CFindReplaceDialog::Create.md)|Erstellt `CFindReplaceDialog` und zeigt ein Dialogfeld an.|  
|[CFindReplaceDialog::FindNext](../Topic/CFindReplaceDialog::FindNext.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das nächste Vorkommen der Suchzeichenfolge finden möchte.|  
|[CFindReplaceDialog::GetFindString](../Topic/CFindReplaceDialog::GetFindString.md)|Rufen Sie diese Funktion auf, um die aktuelle Suchzeichenfolge abzurufen.|  
|[CFindReplaceDialog::GetNotifier](../Topic/CFindReplaceDialog::GetNotifier.md)|Rufen Sie diese Funktion auf, um die **FINDREPLACE**\-Struktur im registrierten Meldungshandler abzurufen.|  
|[CFindReplaceDialog::GetReplaceString](../Topic/CFindReplaceDialog::GetReplaceString.md)|Rufen Sie diese Funktion auf, um die aktuelle Ersetzungszeichenfolge abzurufen.|  
|[CFindReplaceDialog::IsTerminating](../Topic/CFindReplaceDialog::IsTerminating.md)|Rufen Sie diese Funktion, um zu bestimmen, ob das Dialogfeld beendet wird.|  
|[CFindReplaceDialog::MatchCase](../Topic/CFindReplaceDialog::MatchCase.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer den Fall von der Suchzeichenfolge genau übereinstimmen möchte.|  
|[CFindReplaceDialog::MatchWholeWord](../Topic/CFindReplaceDialog::MatchWholeWord.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer nur ganze Wörter entsprechen möchte.|  
|[CFindReplaceDialog::ReplaceAll](../Topic/CFindReplaceDialog::ReplaceAll.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer alle Vorkommen der Zeichenfolge ersetzt werden wünscht.|  
|[CFindReplaceDialog::ReplaceCurrent](../Topic/CFindReplaceDialog::ReplaceCurrent.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer das aktuelle Wort ersetzt werden wünscht.|  
|[CFindReplaceDialog::SearchDown](../Topic/CFindReplaceDialog::SearchDown.md)|Rufen Sie diese Funktion, um zu bestimmen, ob der Benutzer die Suche in eine Abwärtsrichtung fortfahren wünscht.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFindReplaceDialog::m\_fr](../Topic/CFindReplaceDialog::m_fr.md)|Eine Struktur verwendet, um ein `CFindReplaceDialog`\-Objekt anzupassen.|  
  
## Hinweise  
 Im Gegensatz zu den anderen Windows\-häufigverwendetes Dialogfeld sind `CFindReplaceDialog`\-Objekte nicht modale und ermöglichen Benutzern, um mit anderen Fenstern zu interagieren, während es auf dem Bildschirm sind.  Es gibt zwei Arten von `CFindReplaceDialog`\-Objekte: Suchendialogfelder und Suchen\/ersetzen Dialogfelder.  Obwohl die Dialogfelder den Benutzer zur Eingabesuche und zur Suche\/zu den Ersetzungszeichenfolgen ermöglichen, verwenden sie keine der suchenden oder ersetzenden Funktionen.  Sie müssen diese der Anwendung hinzufügen.  
  
 Um ein `CFindReplaceDialog`\-Objekt zu erstellen, verwenden Sie den bereitgestellten Konstruktor \(den keine Argumente enthält\).  Da dies ein nicht modales Dialogfeld handelt, ordnen Sie das Objekt auf dem Heap mithilfe des Operators **new**, anstatt auf dem Stapel.  
  
 Sobald ein `CFindReplaceDialog`\-Objekt erstellt wurde, müssen Sie die [Erstellen Sie](../Topic/CFindReplaceDialog::Create.md)\-Memberfunktion aufrufen, um das Dialogfeld zu erstellen und anzuzeigen.  
  
 Verwenden Sie die [m\_fr](../Topic/CFindReplaceDialog::m_fr.md)\-Struktur, um das Dialogfeld zu initialisieren, bevor Sie **Create** aufrufen.  Die `m_fr`\-Struktur ist vom Typ [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835).  Weitere Informationen über diese Struktur, finden Sie unter [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Damit das übergeordnete Fenster der Ermittlung benachrichtigt werden kann\/ersetzen Sie Anforderungen, müssen Sie die Funktion Windows [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) verwenden und das [ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md) Meldungszuordnungsmakro im Rahmenfenster verwenden, das diese registrierte Meldung verarbeitet.  
  
 Sie können bestimmen, ob der Benutzer entschieden hat, um das Dialogfeld mit der `IsTerminating`\-Memberfunktion zu beenden.  
  
 `CFindReplaceDialog` beruht auf der COMMDLG.DLL\-Datei, die mit Windows\-Versionen 3,1 und höher bereitgestellt wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFindReplaceDialog`, erstellen Sie eine benutzerdefinierte Dialogfeldvorlage, und fügen Sie eine Meldungszuordnung hinzu um die Benachrichtigungsmeldungen aus den erweiterten \- Steuerelementen verarbeiten.  Alle nicht verarbeiteten Nachrichten sollten die Basisklasse übergeben werden.  
  
 Die Hookfunktion anzupassen ist nicht erforderlich.  
  
 Weitere Informationen zur Verwendung von `CFindReplaceDialog`, finden Sie unter [Allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## Anforderungen  
 **Header:**  afxdlgs.h  
  
## Siehe auch  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)