---
title: "Schnittstellenelemente"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Architektur [C++], MFC-Feature Pack"
  - "MFC-Feature Pack, Architektur"
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
caps.latest.revision: 28
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# Schnittstellenelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument beschreibt Schnittstellenelemente, die in [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] SP1 eingeführt wurden, und beschreibt außerdem Unterschiede mit der vorherigen Version der Bibliothek.  
  
 Die folgende Abbildung zeigt eine Anwendung, die erstellt wurde, indem die neuen Schnittstellenelemente verwendet.  
  
 ![Beispielanwendung für das MFC&#45;Feature Pack](../mfc/media/mfc_featurepack.png "MFC\_FeaturePack")  
  
## Fenster\-Andocken  
 Fensterandockenfunktionalität ähnelt dem Fensterandocken, das die grafische Benutzeroberfläche [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] verwendet.  
  
## Steuerleisten ist jetzt Bereiche  
 Steuerleisten nun wird als Bereiche und sind von [CBasePane Class](../mfc/reference/cbasepane-class.md) abgeleitet.  In früheren Versionen von MFC, war die Basisklasse von Steuerleisten `CControlBar`.  
  
 Das Anwendungshauptrahmenfenster wird normalerweise von [CFrameWndEx Class](../mfc/reference/cframewndex-class.md) oder [CMDIFrameWndEx\-Klasse](../mfc/reference/cmdiframewndex-class.md) dargestellt.  Der Hauptframes wird die *Docksite* aufgerufen.  Bereiche können einen von drei Typen übergeordnete Elemente verfügen: eine Docksite, eine Dockleiste oder bleiben ein.  
  
 Es gibt zwei Typen von Bereichen: nicht\-in der Größe veränderbar und in der Größe veränderbar.  In der Größe veränderbare Bereiche, z Statusleisten oder Symbolleisten, können angepasst werden, indem Splitter oder Schieberegler verwendet.  In der Größe veränderbare Bereiche können Container zusammensetzt \(ein Bereich kann in einen anderen Gültigkeitsbereich angedockt werden und einen Splitter dazwischen erstellen\).  Allerdings können in der Größe veränderbare Bereiche nicht angehängt werden \(angedockt wurde\) um Balken anzudocken.  
  
 Wenn die Anwendung nicht\-inder Größe veränderbare Bereiche verwendet, leiten Sie diese von der [CPane Class](../mfc/reference/cpane-class.md).  Wenn die Anwendung in der Größe veränderbare Bereiche verwendet, leiten Sie diese von der [CDockablePane Class](../mfc/reference/cdockablepane-class.md)  
  
## Docken Sie Website an  
 Die Docksite \(oder das Hauptrahmenfenster\) besitzt alle Bereiche und bleiben in einer Anwendung.  Die Docksite enthält einen [CDockingManager](../mfc/reference/cdockingmanager-class.md)\-Member.  Dieser Member wird eine Liste aller Bereiche, die der Docksite gehören.  Die Liste wird sortiert, sodass die Bereiche, die an den Außenkanten der Docksite erstellt werden, am Anfang der Liste platziert werden.  Wenn das Framework die Docksite neu zeichnet, wenn es über dieser Liste und passt das Layout jedes Panels, um das aktuelle umschließende Rechteck der Docksite überspannt.  Sie können `AdjustDockingLayout` oder `RecalcLayout` aufrufen, wenn Sie das Andockenlayout anpassen müssen, und das Framework leitet diesen Aufruf an Andockenmanager um.  
  
## Dock\-Leisten  
 Jedes Hauptrahmenfenster kann *Dockleisten* entlang seinen Rändern positionieren.  Eine Dockleiste ist ein Bereich, der die [CDockSite Class](../mfc/reference/cdocksite-class.md) gehört.  Dockleisten können die Objekte übernehmen, die von [CPane](../mfc/reference/cpane-class.md), wie Symbolleisten abgeleitet werden.  Um Dockleisten erstellen wenn das Hauptrahmenfenster initialisiert wird, rufen Sie `EnableDocking` auf.  Um benutzerdefinierte " Automatisch im Hintergrund zu aktivieren, rufen `EnableAutoHideBars` auf.  `EnableAutoHideBars` erstellt Objekte [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) und positioniert sie neben jeder Dockleiste.  
  
 Jede Dockleiste wird in Dockzeilen unterteilt.  Dockzeilen werden von [CDockingPanesRow Class](../mfc/reference/cdockingpanesrow-class.md) dargestellt.  Jede Dockzeile enthält eine Liste der Symbolleisten.  Wenn ein Benutzer eine Symbolleiste Andocken oder die Symbolleiste aus einer Zeile auf andere in derselben Dockleiste bewegt, erstellt das Framework entweder eine neue Zeile und ändert die Dockleiste entsprechend Größe, oder es positioniert die Symbolleiste auf eine vorhandene Zeile.  
  
## Minirahmen Windows  
 Ein beweglicher Bereich befindet sich in einem Minirahmenfenster dargestellt.  Minirahmenfenster werden durch zwei Klassen dargestellt: [CMDITabInfo Class](../mfc/reference/cmditabinfo-class.md) \(die nur einen Bereich enthalten kann\) und [CMultiPaneFrameWnd Class](../mfc/reference/cmultipaneframewnd-class.md) \(die einige Bereiche\) enthalten kann.  Um einen Bereich im Code anzuzeigen Float, rufen Sie [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) auf.  Nach einem Bereich an, bietet das Framework automatisch ein Minirahmenfenster erstellt und dieses Minirahmenfenster unverankerte wird das übergeordnete Element des Bereichs.  Wenn der unverankerte Panel andocken, aktiviert das Framework das übergeordnete Element zurück, und die unverankerte Bereich wird eine Dockleiste \(für Symbolleisten\) oder eine Docksite \(für größenveränderbare Bereiche\).  
  
## Bereichs\-Teiler  
 Die Bereichsteiler \(auch " Schieberegler oder Splitter\) werden von [CPaneDivider Class](../mfc/reference/cpanedivider-class.md) dargestellt.  Wenn ein Benutzer einem Panel andocken würde, erstellt das Framework Bereichsteiler, unabhängig davon, ob der Bereich an der Docksite oder einen anderen Bereich angedockt ist.  Wenn ein Bereich zur Docksite Andocken, wird der Bereichsteiler den *Standardbereichsteiler* aufgerufen.  Der Standardbereichsteiler ist für das Layout Andockenbereiche aller in der Docksite zuständig.  Der Dockmanager verwaltet eine Liste von Standardbereichsteilern und eine mit Bereichen.  Dockmanager sind für das Layout der Andockenbereiche zuständig.  
  
## Container  
 Alle in der Größe veränderbaren Bereichen, wenn sie miteinander angedockt, werden in den Containern beibehalten.  Container werden von [CPaneContainer Class](../mfc/reference/cpanecontainer-class.md) dargestellt.  Jeder Container hat Zeiger in den linken Bereich, zu rechten Bereich, zu Untercontainer linken, rechten und zu Untercontainer den Splitter zwischen dem linken und rechten Teilen. \(*Link und rechts* verweisen Sie nicht an, physische Seiten jedoch bestimmen Sie eher die Verzweigungen einer Struktur.\) Auf diese Weise können Sie eine Struktur von Bereichen und von Splittern erstellen und komplexe, Layouts von Bereichen daher zu erzielen, die zusammen Größe geändert werden können.  Die `CPaneContainer`\-Klasse behält die Struktur von Containern bei; führt jedoch auch zwei Listen von Bereichen und Farbschiebereglers, die in dieser Struktur befinden.  Bereichscontainermanager werden normalerweise in Standardschieberegler und in Minirahmenfenster eingebettet, die mehrere Bereiche beeinflusst.  
  
## Steuerleisten " Automatisch im Hintergrund  
 Standardmäßig unterstützt jede `CDockablePane` die Funktion " Automatisch im Hintergrund.  Wenn ein Benutzer auf das Drehfeld in der Titelleiste `CDockablePane` klicken, wechselt das Framework den Bereich für den Modus "Automatisches Ausblenden" um.  Um den Mausklick zu behandeln, erstellt das Framework [CMFCAutoHideBar Class](../mfc/reference/cmfcautohidebar-class.md) und [CMFCAutoHideButton Class](../mfc/reference/cmfcautohidebutton-class.md), die mit dem `CMFCAutoHideBar`\-Objekt zugeordnet werden.  Das Framework setzt neue `CMFCAutoHideBar` auf [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md).  Das Framework fügt auch `CMFCAutoHideButton` zur Symbolleiste an.  [CDockingManager Class](../mfc/reference/cdockingmanager-class.md) wartet `CDockablePane`.  
  
## Steuerleisten im Registerkartenformat und Outlook\-Leisten  
 [CMFCBaseTabCtrl Class](../mfc/reference/cmfcbasetabctrl-class.md) implementiert die Basisfunktionen eines Fensters im Registerkartenformat mit abnehmbaren Registerkarten.  Um ein `CMFCBaseTabCtrl`\-Objekt zu verwenden, initialisieren Sie [CBaseTabbedPane\-Klasse](../mfc/reference/cbasetabbedpane-class.md) in der Anwendung.  `CBaseTabbedPane` ist von `CDockablePane` abgeleitet und einen Zeiger auf ein `CMFCBaseTabCtrl`\-Objekt wartet.  `CBaseTabbedPane`, damit Benutzer anzudocken und angepasst Steuerleisten im Registerkartenformat.  Verwenden Sie [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md), Steuerleisten dynamisch erzeugen, die verankert und angesteuert werden.  
  
 Das Outlook\-Leistensteuerelement basiert auch auf Balken im Registerkartenformat.  [CMFCOutlookBar\-Klasse](../mfc/reference/cmfcoutlookbar-class.md) ist von `CBaseTabbedPane` abgeleitet.  Weitere Informationen dazu, wie Outlook\-Leiste, finden Sie unter [CMFCOutlookBar\-Klasse](../mfc/reference/cmfcoutlookbar-class.md).  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)