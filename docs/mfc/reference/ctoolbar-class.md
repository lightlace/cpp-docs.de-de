---
title: "CToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bitmaps [C++], button controls"
  - "Schaltflächen [C++], MFC toolbars"
  - "control bars [C++], CToolBar class"
  - "CToolBar class"
  - "Symbolleisten [C++], CToolBar class"
  - "Windows common controls [C++], CToolBar class"
  - "Windows toolbar common controls [C++]"
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Steuerleisten, die eine Zeile von geherstellten Schaltflächen und von optionalen Trennzeichen haben.  
  
## Syntax  
  
```  
class CToolBar : public CControlBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CToolBar::CToolBar](../Topic/CToolBar::CToolBar.md)|Erstellt ein `CToolBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](../Topic/CToolBar::CommandToIndex.md)|Gibt den Index einer Schaltfläche mit der angegebenen Befehl ID zurück|  
|[CToolBar::Create](../Topic/CToolBar::Create.md)|Stellt die Windows\-Symbolleiste erstellt und fügt sie dem `CToolBar`\-Objekt.|  
|[CToolBar::CreateEx](../Topic/CToolBar::CreateEx.md)|Erstellt ein Objekt `CToolBar` mit zusätzlichen Formaten für das eingebettete `CToolBarCtrl`\-Objekt.|  
|[CToolBar::GetButtonInfo](../Topic/CToolBar::GetButtonInfo.md)|Ruft die ID, das Format und die Imagezahl einer Schaltfläche ab.|  
|[CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md)|Ruft das Format für eine Schaltfläche ab.|  
|[CToolBar::GetButtonText](../Topic/CToolBar::GetButtonText.md)|Ruft den Text ab, der auf einer Schaltfläche angezeigt wird.|  
|[CToolBar::GetItemID](../Topic/CToolBar::GetItemID.md)|Gibt die Befehls\-ID einer Schaltfläche oder eines Trennzeichens am angegebenen Index zurück.|  
|[CToolBar::GetItemRect](../Topic/CToolBar::GetItemRect.md)|Ruft das Anzeigenrechteck für das Element am angegebenen Index ab.|  
|[CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)|Ermöglicht Zugriff auf die zugrunde liegenden allgemeine Steuerelemente.|  
|[CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)|Lädt die Bitmap, die BitmapSchaltfläche Bilder enthält.|  
|[CToolBar::LoadToolBar](../Topic/CToolBar::LoadToolBar.md)|Lädt eine Symbolleistenressource, die mit dem Ressourcen\-Editor erstellt wird.|  
|[CToolBar::SetBitmap](../Topic/CToolBar::SetBitmap.md)|Legt ein Bitmapbild fest.|  
|[CToolBar::SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)|Legt die ID, das Format und die Imagezahl einer Schaltfläche fest.|  
|[CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)|Sätze Schaltfläche Formate und einen Index von Schaltflächenbilder innerhalb der Bitmaps.|  
|[CToolBar::SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md)|Legt das Format für eine Schaltfläche fest.|  
|[CToolBar::SetButtonText](../Topic/CToolBar::SetButtonText.md)|Legt den Text fest, der auf einer Schaltfläche angezeigt wird.|  
|[CToolBar::SetHeight](../Topic/CToolBar::SetHeight.md)|Gibt die Höhe der Symbolleiste fest.|  
|[CToolBar::SetSizes](../Topic/CToolBar::SetSizes.md)|Legt die Größen von Schaltflächen und deren Bitmaps fest.|  
  
## Hinweise  
 Die Schaltflächen können wie Pushbuttone, Kontrollkästchenschaltflächen oder Optionsfelder verhalten.  `CToolBar`\-Objekte sind normalerweise eingebettete Member von den Rahmenfensterobjekten, die von der Klasse [CFrameWnd](../../mfc/reference/cframewnd-class.md) oder [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) abgeleitet werden.  
  
 [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md), eine Memberfunktion, die MFC 4.0 neu ist, ermöglicht es Ihnen, die Unterstützung des allgemeinen Windows\-Steuerelements für Symbolleistenanpassung und \-zusätzliche Funktionen zu nutzen.  `CToolBar`\-Memberfunktionen geben Sie den Großteil der Funktionalität der allgemeinen Windows\-Steuerelemente; Wenn Sie jedoch `GetToolBarCtrl` aufrufen, können Sie den Symbolleisten noch mehr der Eigenschaften von Windows 95\/98\-Symbolleisten geben.  Wenn Sie `GetToolBarCtrl` aufrufen, gibt es einen Verweis auf ein Objekt `CToolBarCtrl` zurück.  Siehe [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) weitere Informationen zum Entwerfen von Symbolleisten mithilfe der allgemeinen Windows\-Steuerelemente.  Weitere allgemeine Informationen über allgemeine Steuerelemente finden Sie unter [Allgemeine Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Visual C\+\+ stellt Ihnen zwei Methoden, um eine Symbolleiste zu erstellen.  Um eine Symbolleistenressource mit dem Ressourcen\-Editor zu erstellen, führen Sie folgende Schritte aus:  
  
1.  Erstellen Sie eine Symbolleistenressource.  
  
2.  Erstellen Sie das `CToolBar`\-Objekt.  
  
3.  Rufen Sie die Funktion [Erstellen Sie](../Topic/CToolBar::Create.md) \(oder [CreateEx](../Topic/CToolBar::CreateEx.md)\) auf, um die Windows\-Symbolleiste erstellen und sie zum `CToolBar`\-Objekt anzufügen.  
  
4.  Aufruf [LoadToolBar](../Topic/CToolBar::LoadToolBar.md), um die Symbolleistenressource zu laden.  
  
 Führen Sie andernfalls folgende Schritte aus:  
  
1.  Erstellen Sie das `CToolBar`\-Objekt.  
  
2.  Rufen Sie die Funktion [Erstellen Sie](../Topic/CToolBar::Create.md) \(oder [CreateEx](../Topic/CToolBar::CreateEx.md)\) auf, um die Windows\-Symbolleiste erstellen und sie zum `CToolBar`\-Objekt anzufügen.  
  
3.  Rufen Sie [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) auf, um die Bitmap zu laden, die die Symbolleistenschaltflächenimages enthält.  
  
4.  Rufen Sie [SetButtons](../Topic/CToolBar::SetButtons.md) auf, um das Schaltflächenformat festzulegen und jede Schaltfläche mit einem Bild in der Bitmap zuzuordnen.  
  
 Alle Schaltflächenbilder kann in der Symbolleiste werden von einer Bitmap übernommen, die ein Bild für jede Schaltfläche enthalten muss.  Alle Bilder müssen die gleiche Größe sein; Standard ist 16 Pixel breit und 15 Pixel hoch.  Bilder müssen in der Bitmap parallel sein.  
  
 Die `SetButtons`\-Funktion nimmt einen Zeiger auf ein Array von Steuer\-IDs und ganzer Zahl, die die Anzahl der Elemente im Array angibt.  Die Funktion legt die ID jeder Schaltfläche auf den Wert des entsprechenden Elements des Arrays fest und weist jeder Schaltfläche einen Bildindex zu, der die Position des Bilds der Schaltfläche in der Bitmap angibt.  Wenn ein Arrayelement den Wert **ID\_SEPARATOR** verfügt, wird kein Bildindex zugewiesen.  
  
 Die Reihenfolge der Bilder in der Bitmap ist in der Regel die Reihenfolge, in der sie auf dem Bildschirm gezeichnet werden, aber Sie können die [SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)\-Funktion verwenden, um die Beziehung zwischen Imagereihenfolge und Zeichnungsreihenfolge zu ändern.  
  
 Alle Schaltflächen in einer Symbolleiste sind die gleiche Größe.  Der Standardwert entspricht 24 x 22 Pixel, in Übereinstimmung mit *Windows\-Oberflächen\-Richtlinien für Softwareentwurf* aus.  Jedes zusätzliche Leerzeichen zwischen dem Bild und den Schaltflächendimensionen wird verwendet, um einen Rahmen um das Bild zu bilden.  
  
 Jede Schaltfläche verfügt über ein Bild.  Die verschiedene Schaltfläche zeigt an und die Formate \(gedrückt, oben unten deaktiviert, unten deaktiviert und unbegrenzt\) werden von diesem einem Bild generiert.  Obwohl Bitmaps jede Farbe sein können, können Sie die besten Ergebnisse mit Bildern in Schwarz und in den in erreichen.  
  
> [!WARNING]
>  `CToolBar` unterstützt Bitmaps mit maximal 16 Farben.  Wenn Sie ein Bild in einen Symbolleisteneditor laden, konvertiert Visual Studio automatisch das Bild in einer Farbe 16, die ggf. Bitmapdatei ist und zeigt eine Warnmeldung an, wenn das Bild konvertiert wurde.  Wenn Sie ein Bild mit mehr als 16 Farben \(mithilfe eines externen Editor, um des Bilds zu bearbeiten\) verwenden, Vorkommnisse die Anwendung möglicherweise unerwartetes.  
  
 Symbolleisten\-Schaltflächen ahmen Pushbuttone standardmäßig nach.  Sie können jedoch Symbolleisten\-Schaltflächen Kontrollkästchenschaltflächen oder \-Optionsfelder auch imitieren.  Kontrollkästchenschaltflächen haben drei Zustände: überprüft, gelöscht und unbestimmt.  Optionsfelder haben nur zwei Zustände: überprüft und gelöscht.  
  
 Um ein einzelnes Schaltflächen\- oder Trennzeichenformat ohne zu zeigen festzulegen zu einem Array, rufen Sie [GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) um das Format ab, und rufen Sie dann [SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md) anstelle `SetButtons` auf.  `SetButtonStyle` ist besonders hilfreich, wenn Sie das Format einer Schaltfläche zur Laufzeit ändern möchten.  
  
 Um Text zuzuweisen um auf einer Schaltfläche anzuzeigen, rufen Sie auf [GetButtonText](../Topic/CToolBar::GetButtonText.md) um den Text abzurufen um auf der Schaltfläche angezeigt wird, und rufen Sie dann auf [SetButtonText](../Topic/CToolBar::SetButtonText.md) um den Text festzulegen.  
  
 Um eine Kontrollkästchenschaltfläche zu erstellen, und weisen Sie ihr das Format **TBBS\_CHECKBOX** zu oder verwenden Sie `SetCheck`\-Memberfunktion eines `CCmdUI`\-Objekts in einem `ON_UPDATE_COMMAND_UI`\-Handler.  Das Aufrufen von `SetCheck` macht einen Pushbutton auf eine Kontrollkästchenschaltfläche.  Führen Sie `SetCheck` ein Argument von 0 für deaktiviertes, 1 für überprüft oder 2 für die.  
  
 Um ein Optionsfeld zu erstellen, rufen Sie [SetRadio](../Topic/CCmdUI::SetRadio.md)\-Memberfunktion [CCmdUI](../../mfc/reference/ccmdui-class.md) eines Objekts aus einem `ON_UPDATE_COMMAND_UI`\-Handler auf.  Führen Sie `SetRadio` ein Argument von 0 für deaktiviertes oder ungleich 0 \(null\) für überprüft.  So fügen Sie einer Optionsfeldgruppe gegenseitig \- exklusives Verhalten bereitstellen, müssen Sie `ON_UPDATE_COMMAND_UI`\-Handler für alle Schaltflächen in der Gruppe haben.  
  
 Weitere Informationen zur Verwendung von `CToolBar`, finden Sie im Artikel [MFC\-Symbolleisten\-Implementierung](../../mfc/mfc-toolbar-implementation.md) und [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC Sampling CTRLBARS](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DLGCBR32](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DOCKTOOL](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CToolBar::Create](../Topic/CToolBar::Create.md)   
 [CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)   
 [CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)   
 [CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)   
 [CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)