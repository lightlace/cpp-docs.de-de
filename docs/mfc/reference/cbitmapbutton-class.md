---
title: "CBitmapButton Class"
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
  - "CBitmapButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitmaps, button controls"
  - "Schaltflächen, Bitmap"
  - "CBitmapButton class"
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmapButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt die Pushbutton\-Steuerelemente, die mit Bitmapbildern anstelle von Text bezeichnet werden.  
  
## Syntax  
  
```  
class CBitmapButton : public CButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md)|Erstellt ein `CBitmapButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](../Topic/CBitmapButton::AutoLoad.md)|Ordnet eine Schaltfläche in einem Dialogfeld mit einem Objekt der Klasse zu `CBitmapButton`, lädt die Bitmaps nach Namen sortiert und die Schaltfläche, um die Bitmap anzupassen.|  
|[CBitmapButton::LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md)|Initialisiert das Objekt durch das Laden einer oder mehrerer benannten Bitmapressourcen aus der Ressourcendatei der Anwendung und das Anfügen der Bitmap in das Objekt.|  
|[CBitmapButton::SizeToContent](../Topic/CBitmapButton::SizeToContent.md)|Sortiert die Schaltfläche, um die Bitmap anzupassen.|  
  
## Hinweise  
 `CBitmapButton`\-Objekte enthalten bis vier Bitmaps, die Bilder für die verschiedenen Zustände enthalten, die, eine Schaltfläche annehmen kann: in \(oder normal\), unten \(oder ausgewählt\), liegt und deaktiviert.  Nur die erste Bitmap ist erforderlich; die anderen sind optional.  
  
 Bitmap\-Schaltfläche Bilder enthalten den Rahmen um das Bild sowie das Bild selbst.  Der Rahmen gibt in der Regel eine Rolle erneut, wenn er den Zustand der Schaltfläche angezeigt wird.  Beispielsweise ist die Bitmap für den Zustand zu normalerweise als der für den hohen Zustand jedoch mit einer gestrichelten Rechteckeinfügung vom Rand oder einer starken durchgezogenen Linie am Rahmen.  Die Bitmap für den deaktivierten Zustand normalerweise ähnelt, dem für den hohen Zustand hat jedoch niedrigerer dazu \(wie eine abgeblendete oder abgeblendete Menüauswahl\).  
  
 Diese Bitmaps können von jeder Größe sein, aber alle werden behandelt, als ob sie die gleiche Größe wie die Bitmap für den hohen Zustand waren.  
  
 Verschiedene Anwendungen fordern verschiedene Kombinationen von Bitmap\-Bildern:  
  
|Nach oben|Nach unten|Focused|Disabled|Anwendung|  
|---------------|----------------|-------------|--------------|---------------|  
|×||||Bitmap|  
|×|×|||Schaltfläche ohne **WS\_TABSTOP** Format|  
|×|×|×|×|Dialogfeldschaltfläche mit allen Zustände|  
|×|×|×||Dialogfeldschaltfläche mit **WS\_TABSTOP** Format|  
  
 Als BitmapSchaltfläche, ein Steuerelement zu erstellen, legen Sie das **BS\_OWNERDRAW** Format fest, um anzugeben, dass die Schaltfläche Ownerdrawn ist.  Dadurch wird Windows, die `WM_MEASUREITEM` und `WM_DRAWITEM` Meldungen für die Schaltfläche zu senden, das Framework diese Meldungen bearbeitet und verwaltet die Darstellung der Schaltfläche für Sie.  
  
### So fügen Sie ein BitmapSchaltfläche Steuerelement im Clientbereich eines Fensters erstellen  
  
1.  Erstellen Sie eine bis vier Bitmapbilder für die Schaltfläche.  
  
2.  Erstellen Sie das [CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md)\-Objekt.  
  
3.  Rufen Sie die [Erstellen Sie](../Topic/CButton::Create.md)\-Funktion auf, um das Schaltflächen\-Steuerelement von Windows zu erstellen und auf `CBitmapButton`\-Objekt anzufügen.  
  
4.  Rufen Sie die [LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md)\-Memberfunktion auf, um die Bitmapressourcen zu laden, nachdem die Bitmapschaltfläche erstellt wurde.  
  
### So BitmapSchaltfläche ein Steuerelement in einem Dialogfeld einschließen  
  
1.  Erstellen Sie eine bis vier Bitmapbilder für die Schaltfläche.  
  
2.  Erstellen Sie eine Dialogfeldvorlage mit einer positionierten Ownerdrawnschaltfläche, wo Sie die Bitmapschaltfläche soll.  Die Größe der Schaltfläche in der Vorlage ist nicht von Bedeutung.  
  
3.  Legen Sie die Beschriftung der Schaltfläche auf einen Wert wie "**MYIMAGE**" festgelegt und definieren Sie ein Symbol für die Schaltfläche wie **IDC\_MYIMAGE**.  
  
4.  im Ressourcenskript der Anwendung geben Sie jedes der Bilder, die für die Schaltfläche eine ID erstellt werden, die mit einem der Buchstaben U "," D "," F "," oder "X" erstellt wird \(für oben und unten liegt deaktiviert\) zur Zeichenfolge anfügen, die für die Schaltflächenbeschriftung in Schritt 3.  Für die Schaltflächenbeschriftung ","**MYIMAGE** beispielsweise, würden die IDs sein **MYIMAGEU**","**MYIMAGED**,"**MYIMAGEF**," und "**MYIMAGEX**." Sie **must** geben die ID der Bitmaps innerhalb der doppelten Anführungszeichen.  Andernfalls weist der Ressourcen\-Editor eine ganze Zahl die Ressource zu und MFC fehl, wenn das Bild lädt.  
  
5.  In der Dialogfeldklasse der Anwendung \(abgeleitet von `CDialog`\), fügen Sie ein `CBitmapButton`\-Memberobjekt hinzu.  
  
6.  In der des `CDialog`[OnInitDialog](../Topic/CDialog::OnInitDialog.md) Routine Objekts rufen Sie die Funktion des `CBitmapButton`[Automatisches Aufladen](../Topic/CBitmapButton::AutoLoad.md)\-Objekts mit als Parameter der Steuerelement\-ID der Schaltfläche und dem des `CDialog`**this** Zeiger Objekts auf.  
  
 Wenn Sie behandeln möchten, Windows\-Benachrichtigungsmeldungen, wie **BN\_CLICKED** gesendet, durch ein BitmapSchaltfläche Steuerelement zu seinem übergeordneten Element \(normalerweise fügen eine Klasse, die von **CDialog\)** abgeleitet ist, `CDialog` von abgeleitetes Objekt eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion für jede Meldung hinzu.  Die Benachrichtigungen, die durch ein `CBitmapButton`\-Objekt gesendet werden, sind identisch mit denen, die von einem [CButton](../../mfc/reference/cbutton-class.md)\-Objekt gesendet werden.  
  
 Die Klasse [CToolBar](../../mfc/reference/ctoolbar-class.md) wählt einen anderen Ansatz zu den Schaltflächen.  
  
 Weitere Informationen zu `CBitmapButton`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC Sampling CTRLTEST](../../top/visual-cpp-samples.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)