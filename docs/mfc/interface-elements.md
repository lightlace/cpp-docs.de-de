---
title: Schnittstellenelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25f9de4ab5f7d12d240625e0fdf5f857563e8ce2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352576"
---
# <a name="interface-elements"></a>Schnittstellenelemente
Dieses Dokument beschreibt die Elemente der Benutzeroberfläche, die in eingeführt wurden [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] SP1 sowie eine Beschreibung von Unterschieden mit der früheren Version der Bibliothek.  
  
 Die folgende Abbildung zeigt eine Anwendung, die mit der neuen Elemente der Benutzeroberfläche erstellt wurde.  
  
 ![MFC-Feature Pack-beispielanwendung](../mfc/media/mfc_featurepack.png "Mfc_featurepack")  
  
## <a name="window-docking"></a>Andocken von Fenstern  
 Fenster, die Andocken Funktionalität ähnelt dem Fenster andocken, die die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] grafischen Benutzeroberfläche verwendet.  
  
## <a name="control-bars-are-now-panes"></a>Steuerleisten sind jetzt Bereiche  
 Steuerleisten werden jetzt als Bereiche bezeichnet und von abgeleitet sind [CBasePane Klasse](../mfc/reference/cbasepane-class.md). In früheren Versionen von MFC die Basisklasse von Steuerleisten wurde `CControlBar`.  
  
 Das Hauptrahmenfenster Anwendung ist normalerweise dargestellt durch die [CFrameWndEx Klasse](../mfc/reference/cframewndex-class.md) oder [CMDIFrameWndEx-Klasse](../mfc/reference/cmdiframewndex-class.md). Der Hauptframe heißt die *Andocken Standort*. Bereiche können einen von drei Typen von übergeordneten Elementen verfügen: eine docksite, ein Strich andocken oder ein Minirahmenfenster.  
  
 Es gibt zwei Arten von Bereichen: nicht veränderbare Größen und geändert werden kann. In der Größe veränderbaren Bereiche, z. B. Statusleisten und Symbolleisten, können mithilfe von Bereichen oder Schieberegler geändert werden. In der Größe veränderbaren Bereiche können Container bilden (ein Bereich kann zu einem anderen Bereich, erstellen eine Aufteilung dazwischen angedockt werden). Allerdings können nicht in der Größe veränderbaren Bereiche (angedockt), um Balken Andocken angefügt werden.  
  
 Wenn Ihre Anwendung nicht veränderbare Größen Bereiche verwendet werden, leiten Sie daraus [CPane-Klasse](../mfc/reference/cpane-class.md).  Wenn Ihre Anwendung in der Größe veränderbaren Bereiche verwendet werden, leiten Sie daraus [CDockablePane-Klasse](../mfc/reference/cdockablepane-class.md)  
  
## <a name="dock-site"></a>DockPosition  
 Das DockPosition (Hauptrahmenfenster) besitzt, oder alle Bereiche und Minirahmenfenster in einer Anwendung. Der DockPosition enthält eine [CDockingManager](../mfc/reference/cdockingmanager-class.md) Member. Bei diesem Member verwaltet eine Liste aller Bereiche, die an der DockPosition gehören. Die Liste sortiert wird, ist, dass die Bereiche, die an den äußeren Rändern eines der DockPosition erstellt am Anfang der Liste positioniert werden. Wenn das Framework der DockPosition zeichnet, durchläuft dieser Liste und passt das Layout jedes Bereichs des aktuellen umschließenden Rechtecks des der DockPosition einschließen. Sie können Aufrufen `AdjustDockingLayout` oder `RecalcLayout` Wenn Sie am Layout des Docks anpassen und das Framework leitet diesen Aufruf an die Dock-Manager.  
  
## <a name="dock-bars"></a>Andocken Balken  
 Jede Hauptrahmenfenster positionieren kann *Andocken Balken* entlang seiner Grenzen. Dock-Leiste ist ein Bereich, der gehört eine [CDockSite-Klasse](../mfc/reference/cdocksite-class.md). Andocken Balken können vom abgeleiteten Objekte akzeptieren [CPane](../mfc/reference/cpane-class.md), z. B. Symbolleisten. Rufen Sie zum Andocken Balken zu erstellen, bei der Initialisierung des Hauptrahmenfenster `EnableDocking`. Rufen Sie zum automatischen Ausblenden Balken zu aktivieren, `EnableAutoHideBars`. `EnableAutoHideBars` erstellt [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) Objekte und positioniert diese neben jeder Balken andocken.  
  
 Andocken Zeilen wird jeder Balken Andocken unterteilt. Dock-Zeilen werden durch dargestellt die [CDockingPanesRow Klasse](../mfc/reference/cdockingpanesrow-class.md). Jede Zeile Andocken enthält eine Liste der Symbolleisten. Wenn ein Benutzer eine Symbolleiste angedockt oder die Symbolleiste aus einer Zeile in einen anderen innerhalb der gleichen Dock-Leiste verschiebt, das Framework erstellt eine neue Zeile und ändert die Größe der Andocken Leiste entsprechend, oder die Position der Symbolleiste auf einer vorhandenen Zeile.  
  
## <a name="mini-frame-windows"></a>Minirahmenfenster  
 Ein Gleitkommazahl im Bereich befindet sich in einem Minirahmenfenster. Minirahmenfenster werden durch zwei Klassen dargestellt: [CMDITabInfo Klasse](../mfc/reference/cmditabinfo-class.md) (die darf nur einen Bereich) und [CMultiPaneFrameWnd Klasse](../mfc/reference/cmultipaneframewnd-class.md) (die können mehrere Bereiche enthalten). Aufrufen, um einen Bereich in Ihrem Code float, [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane). Nach ein Bereich befindet, erstellt das Framework automatisch ein Minirahmenfenster und diese Minirahmenfenster wird das unverankerte Bereich übergeordnetes Element. Wenn schwebende Fenster angedockt, das Framework wird zurückgesetzt, die das übergeordnete Element und das unverankerte Fenster kann Andocken Balken (für Symbolleisten) oder (für in der Größe veränderbaren Bereiche) einer docksite.  
  
## <a name="pane-dividers"></a>Bereichsteiler  
 Bereichsteiler (auch als Schieberegler oder Splitterfenstern) dargestellt wird, durch die [CPaneDivider Klasse](../mfc/reference/cpanedivider-class.md). Wenn ein Benutzer einen Bereich angedockt, erstellt das Framework bereichsteiler, unabhängig davon, ob der Bereich an der DockPosition oder an einem anderen Bereich angedockt ist. Bereichsteiler wird aufgerufen, wenn ein Bereich an der DockPosition angedockt, die *Standard bereichsteiler*. Standard-bereichsteiler ist verantwortlich für das Layout der alle andockbare Bereiche der DockPosition. Dock-Manager verwaltet eine Liste der Standard-bereichsteiler, und eine Liste von Bereichen. Dock-Manager sind verantwortlich für das Layout der alle andockbare Bereiche.  
  
## <a name="containers"></a>Container  
 Alle in der Größe veränderbaren Bereiche angedockten zu "other" sind in Containern beibehalten. Container werden durch dargestellt die [CPaneContainer Klasse](../mfc/reference/cpanecontainer-class.md). Jeder Container verfügt Zeigern zu seiner linken, rechten Bereich linken Untercontainer, rechten Untercontainer und der Splitter zwischen den linken und rechten teilen. (*Links* und *rechten* verweisen Sie nicht auf physische Seiten jedoch eher die Verzweigungen, eine Struktur ermittelt werden.) Auf diese Weise kann eine Struktur von Bereichen und Splitterfenstern erstellen und daher erreichen komplexe Layouts von Bereichen, die zusammen Größe geändert werden können. Die `CPaneContainer` Klasse verwaltet die Struktur von Containern, sichert auch zwei Listen von Bereichen und Schieberegler, die in dieser Struktur befinden. Bereich Container-Manager werden in der Regel in der Standardeinstellung Schieberegler und Minirahmenfenster, die mehrere Bereiche enthalten eingebettet ist.  
  
## <a name="auto-hide-control-bars"></a>Steuerleisten automatisch im Hintergrund  
 Standardmäßig jede `CDockablePane` unterstützt die Funktion "automatisch im Hintergrund". Wenn ein Benutzer klickt auf die Beschriftung des der `CDockablePane`, das Framework Schaltet den Bereich zum automatischen Ausblendemodus. Behandeln Sie das Klicken auf das Framework erstellt eine [CMFCAutoHideBar-Klasse](../mfc/reference/cmfcautohidebar-class.md) und ein [CMFCAutoHideButton-Klasse](../mfc/reference/cmfcautohidebutton-class.md) zugeordneten der `CMFCAutoHideBar` Objekt. Das Framework setzt das neue `CMFCAutoHideBar` auf die [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md). Das Framework auch fügt die `CMFCAutoHideButton` auf der Symbolleiste. Die [CDockingManager Klasse](../mfc/reference/cdockingmanager-class.md) verwaltet die `CDockablePane`.  
  
## <a name="tabbed-control-bars-and-outlook-bars"></a>Im Registerkartenformat Steuerleisten und Outlook Balken  
 Die [CMFCBaseTabCtrl-Klasse](../mfc/reference/cmfcbasetabctrl-class.md) implementiert die Basisfunktionalität von einem Fenster im Registerkartenformat mit abtrennbaren Registerkarten. Verwenden einer `CMFCBaseTabCtrl` Objekt, das Initialisieren einer [CBaseTabbedPane-Klasse](../mfc/reference/cbasetabbedpane-class.md) in Ihrer Anwendung. `CBaseTabbedPane` stammt aus `CDockablePane` und steht ein Zeiger auf eine `CMFCBaseTabCtrl` Objekt. Die `CBaseTabbedPane` ermöglicht Benutzern das Andocken und Größe der Registerkarten-Steuerelement Balken. Verwendung [CDockablePane:: Attachtotabwnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) Steuerleisten dynamisch zu erstellen, die im Registerformat und angedockt sind.  
  
 Das Outlook-Steuerelement basiert auch auf Balken im Registerkartenformat. Die [CMFCOutlookBar-Klasse](../mfc/reference/cmfcoutlookbar-class.md) stammt aus `CBaseTabbedPane`. Weitere Informationen zur Verwendung von Outlook-Leiste finden Sie unter [CMFCOutlookBar-Klasse](../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)

