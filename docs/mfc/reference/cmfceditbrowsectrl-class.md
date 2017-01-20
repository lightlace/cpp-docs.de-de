---
title: "CMFCEditBrowseCtrl Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCEditBrowseCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCEditBrowseCtrl class"
  - "CMFCEditBrowseCtrl constructor"
  - "CMFCEditBrowseCtrl::PreTranslateMessage method"
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCEditBrowseCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCEditBrowseCtrl`\-Klasse unterstützt das Steuerelement zum Bearbeiten und Durchsuchen, das ein bearbeitbare Textfelder ist, das optional Schaltfläche Durchsuchen enthält.  Wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken, führt das Steuerelement eine benutzerdefinierte Aktion aus oder zeigt ein Standarddialogfeld an, das einen Dateibrowser oder einen Ordnerbrowser enthält.  
  
## Syntax  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Standardkonstruktor.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md)|Aktiviert oder deaktiviert \(\) zeigt die Schaltfläche zum Durchsuchen.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md)|Aktiviert die Schaltfläche zum Durchsuchen und aktiviert das Steuerelement zum Bearbeiten und Navigieren in *Dateidurchsuchen\-modus* ein.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md)|Aktiviert die Schaltfläche zum Durchsuchen und aktiviert das Steuerelement zum Bearbeiten und Navigieren in *Ordnerdurchsuchen\-modus* ein.|  
|[CMFCEditBrowseCtrl::GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md)|Gibt den aktuellen Durchsuchen\-Modus zurück.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](../Topic/CMFCEditBrowseCtrl::OnAfterUpdate.md)|Aufgerufen vom Framework nach dem Steuerelement zum Bearbeiten und Durchsuchen wird mit dem Ergebnis einer Aktion Durchsuchen aktualisiert.|  
|[CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md)|Aufgerufen vom Framework nach dem Benutzer klickt auf die Schaltfläche zum Durchsuchen.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](../Topic/CMFCEditBrowseCtrl::OnChangeLayout.md)|Aktualisiert das aktuelle Steuerelement zum Bearbeiten und Durchsuchen neu.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md)|Aufgerufen durch das Framework, um die Schaltfläche Durchsuchen zu zeichnen.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](../Topic/CMFCEditBrowseCtrl::OnIllegalFileName.md)|Aufgerufen vom Framework, als ein ungültiger Dateiname in das Bearbeitungssteuerelement eingeführt wurde.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  So Syntax und weitere Informationen finden Sie unter [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md)|Legt ein benutzerdefiniertes Bild für die Schaltfläche Durchsuchen fest.|  
  
## Hinweise  
 Verwenden Sie ein Steuerelement zum Bearbeiten und Durchsuchen, um eine Datei oder einen Ordnernamen auszuwählen.  Optional können Sie das Steuerelement, um eine benutzerdefinierte Aktion auszuführen, wie ein Dialogfeld anzuzeigen.  Sie können die Schaltfläche Durchsuchen anzeigen oder nicht anzeigen, und Sie können eine benutzerdefinierte Bezeichnung oder ein Bild auf der Schaltfläche anwenden.  
  
 Der *Durchsuchen\-Modus* des Steuerelements zum Bearbeiten und Durchsuchen bestimmt, ob es Schaltfläche Durchsuchen angezeigt und welche Aktion erfolgt, wenn auf die Schaltfläche geklickt wird.  Weitere Informationen finden Sie in [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md)\-Methode.  
  
 Die `CMFCEditBrowseCtrl`\-Klasse unterstützt die folgenden Modi.  
  
 `custom mode`  
 Eine benutzerdefinierte Aktion wird ausgeführt, wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken.  Beispielsweise können Sie ein anwendungsspezifisches Dialogfeld anzeigen.  
  
 `file mode`  
 Ein Standarddatei\-Auswahldialogfeld wird angezeigt, wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken.  
  
 `folder mode`  
 Ein Standardordner\-Auswahldialogfeld wird angezeigt, wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken.  
  
## Gewusst\-wie\-Themen: Geben Sie ein Steuerelement zum Bearbeiten und Durchsuchen an  
 Führen Sie die folgenden Schritte aus, um ein Steuerelement zum Bearbeiten und Navigieren in der Anwendung zu enthalten:  
  
1.  Wenn Sie einen benutzerdefinierten Durchsuchen\-Modus implementieren möchten, berechnen Sie die eigene Klasse von der Klasse `CMFCEditBrowseCtrl` und überschreiben Sie dann die [CMFCEditBrowseCtrl::OnBrowse](../Topic/CMFCEditBrowseCtrl::OnBrowse.md)\-Methode.  In der überschriebenen Methode führen Sie eine benutzerdefinierte Aktion Navigieren aus und aktualisieren Sie das Steuerelement zum Bearbeiten und zum Durchsuchen mit dem Ergebnis.  
  
2.  Betten Sie entweder das `CMFCEditBrowseCtrl` abgeleitete Objekt oder das Steuerelement zum Bearbeiten und Durchsuchen\-Objekt in das Objekt des übergeordneten Fensters ein.  
  
3.  Wenn Sie **Klassen\-Assistent** verwenden, um ein Dialogfeld zu erstellen, fügen Sie ein Bearbeitungssteuerelement \(`CEdit`\) dem Dialogfeldformular hinzu.  Außerdem fügen Sie eine Variable hinzu, um auf das Steuerelement in der Headerdatei zuzugreifen.  In der Headerdatei ändern Sie den Typ der Variablen von `CEdit` zu `CMFCEditBrowseCtrl`.  Das Steuerelement zum Bearbeiten und Durchsuchen wird automatisch erstellt.  Wenn Sie nicht **Klassen\-Assistent** verwenden, fügen Sie eine `CMFCEditBrowseCtrl`\-Variable der Headerdatei hinzu und rufen Sie dann die `Create`\-Methode auf.  
  
4.  Wenn Sie ein Steuerelement zum Bearbeiten und Durchsuchen einem Dialogfeld hinzufügen, verwenden Sie das Tool, um **ClassWizard** Datenaustausch zu installieren.  
  
5.  Rufen Sie die [EnableFolderBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFolderBrowseButton.md), [EnableFileBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableFileBrowseButton.md) oder [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md)\-Methode auf, um den Durchsuchen\-Modus festzulegen und die Schaltfläche zum Durchsuchen anzuzeigen.  Rufen Sie die Methode auf [GetMode](../Topic/CMFCEditBrowseCtrl::GetMode.md), erhält der aktuelle Durchsuchen\-Modus.  
  
6.  Um ein benutzerdefiniertes Bild für die Schaltfläche Durchsuchen bereitzustellen, rufen Sie die Methode auf [SetBrowseButtonImage](../Topic/CMFCEditBrowseCtrl::SetBrowseButtonImage.md) oder überschreiben Sie die Methode [OnDrawBrowseButton](../Topic/CMFCEditBrowseCtrl::OnDrawBrowseButton.md).  
  
7.  Um die Schaltfläche Durchsuchen vom Steuerelement zum Bearbeiten und Wechseln zu entfernen, rufen Sie die [EnableBrowseButton](../Topic/CMFCEditBrowseCtrl::EnableBrowseButton.md)\-Methode mit dem `bEnable`\-Parameter auf, der zu `FALSE` festgelegt ist.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie zwei Methoden in der Klasse `CMFCEditBrowseCtrl` verwendet: `EnableFolderBrowseButton` und `EnableFileBrowseButton`.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#6)]  
[!CODE [NVC_MFC_NewControls#7](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#7)]  
  
## Anforderungen  
 **Header:** afxeditbrowsectrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)