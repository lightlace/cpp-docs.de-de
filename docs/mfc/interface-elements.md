---
title: Schnittstellenelemente | Microsoft-Dokumentation
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
ms.openlocfilehash: 0f8cb2a8f3ccb36f3fa1ed2bf3f81087691ce988
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404409"
---
# <a name="interface-elements"></a>Schnittstellenelemente

In diesem Dokument wird beschrieben, die Elemente der Benutzeroberfläche, die in Visual Studio 2008 SP1 eingeführt wurden, und beschreibt außerdem die Unterschiede, die mit der früheren Version der Bibliothek.

Die folgende Abbildung zeigt eine Anwendung, die mit die Elemente der neuen Benutzeroberfläche erstellt wurde.

![MFC-Feature Pack-beispielanwendung](../mfc/media/mfc_featurepack.png "Mfc_featurepack")

## <a name="window-docking"></a>Andocken von Fenstern

Andockbare Fenster-Funktionalität ähnelt das Fenster andocken, dass die grafischen Benutzeroberfläche von Visual Studio verwendet.

## <a name="control-bars-are-now-panes"></a>Steuerleisten sind jetzt Bereiche

Steuerleisten werden jetzt als Bereiche und davon abgeleitet sind [CBasePane-Klasse](../mfc/reference/cbasepane-class.md). In früheren Versionen von MFC, wurde die Basisklasse von Steuerleisten `CControlBar`.

Die anwendungshauptrahmenfensters ist normalerweise dargestellt durch die [CFrameWndEx-Klasse](../mfc/reference/cframewndex-class.md) oder [CMDIFrameWndEx-Klasse](../mfc/reference/cmdiframewndex-class.md). Der Hauptframe heißt die *Andocken Site*. Bereiche können einen der drei Typen von übergeordneten Elementen aufweisen: eine docksite, einen Balken andocken oder ein Minirahmenfenster.

Es gibt zwei Arten von Bereichen: nicht veränderbare Größen und geändert werden kann. In der Größe veränderbaren Bereiche, z. B. Statusleisten und Symbolleisten, können geändert werden, mithilfe von Aufteilungen oder Schieberegler. In der Größe veränderbaren Bereiche können Container bilden (ein Bereich kann ein weiterer Bereich, erstellen einen dazwischen befindlichen Splitter angedockt werden). Allerdings können nicht in der Größe veränderbaren Bereiche (angedockt), um Balken anzudocken angefügt werden.

Wenn Ihre Anwendung nicht veränderbare Größen Bereiche verwendet werden, leiten Sie von [CPane-Klasse](../mfc/reference/cpane-class.md).  Wenn Ihre Anwendung in der Größe veränderbaren Bereiche verwendet werden, leiten Sie von [CDockablePane-Klasse](../mfc/reference/cdockablepane-class.md)

## <a name="dock-site"></a>DockPosition

Der DockPosition (oder im Hauptrahmenfenster) besitzt alle Bereiche und Minirahmenfenster in einer Anwendung. Der DockPosition enthält eine [CDockingManager](../mfc/reference/cdockingmanager-class.md) Member. Dieser Member verwaltet eine Liste mit allen Bereichen, die an der DockPosition gehören. Die Liste wird geordnet, sodass die Bereiche am äußeren Rand der DockPosition erstellt am Anfang der Liste platziert werden. Wenn das Framework der DockPosition zeichnet, diese Liste durchläuft und passt das Layout jeder Bereich, um die aktuellen umschließenden Rechtecks des der DockPosition enthalten. Rufen Sie `AdjustDockingLayout` oder `RecalcLayout` beim Layout des Docks angepasst haben, und das Framework leitet dieser Aufruf Dock-Manager.

## <a name="dock-bars"></a>Dock-Balken

Jede Hauptrahmenfenster positionieren kann *Andocken Balken* entlang der Rahmen. Eine Leiste Andocken ist ein Bereich, zu dem gehört eine [CDockSite-Klasse](../mfc/reference/cdocksite-class.md). Dock-Balken abgeleitete Objekte akzeptiert [CPane](../mfc/reference/cpane-class.md), wie beispielsweise Symbolleisten. Rufen Sie zum Andocken Balken zu erstellen, bei der Initialisierung des Hauptrahmenfenster `EnableDocking`. Rufen Sie zum Aktivieren der automatischen Ausblenden Balken `EnableAutoHideBars`. `EnableAutoHideBars` erstellt [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) Objekte und positioniert diese neben jeder Balken andocken.

Jeder Balken Andocken ist in Dock Zeilen unterteilt. Dock-Zeilen werden durch dargestellt die [CDockingPanesRow-Klasse](../mfc/reference/cdockingpanesrow-class.md). Jede Zeile Andocken enthält eine Liste der Symbolleisten. Wenn ein Benutzer eine Symbolleiste angedockt oder die Symbolleiste aus einer Zeile in einen anderen auf dem gleichen Dock Balken angezeigt verschiebt, das Framework erstellt eine neue Zeile, und es die andockziel-Leiste entsprechend ändert oder auf die Position der Symbolleiste auf einer vorhandenen Zeile.

## <a name="mini-frame-windows"></a>Minirahmenfensters Windows

Ein Gleitkommazahl im Bereich befindet sich in einem Minirahmenfenster. Minirahmenfenster durch zwei Klassen dargestellt werden: [CMDITabInfo-Klasse](../mfc/reference/cmditabinfo-class.md) (das kann nur jeweils ein Bereich enthalten) und [CMultiPaneFrameWnd-Klasse](../mfc/reference/cmultipaneframewnd-class.md) (das kann mehrere Bereiche enthalten). Aufrufen, um einen Bereich in Ihrem Code float, [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane). Nachdem ein Bereich wird verschoben, erstellt das Framework automatisch ein Minirahmenfenster und dieser kleinen Rahmenfenster angezeigt wird, der unverankerten Bereichs klicken übergeordnetes Element. Wenn der unverankerten Bereichs klicken dockt an, das Framework wird zurückgesetzt, die das übergeordnete Element und der unverankerten Bereichs klicken wird eine Leiste Dock (für Symbolleisten) oder eine docksite (für in der Größe veränderbaren Fenster).

## <a name="pane-dividers"></a>Bereichsteiler

Bereichsteiler (auch als Schieberegler oder Splitterfenstern bezeichnet) werden durch dargestellt die [CPaneDivider-Klasse](../mfc/reference/cpanedivider-class.md). Wenn ein Benutzer einen Bereich angedockt, erstellt das Framework bereichsteiler, unabhängig davon, ob der Bereich an der DockPosition oder an einem anderen Bereich angedockt ist. Bereichsteiler wird aufgerufen, wenn Sie ein Bereich an der DockPosition angedockt, die *Standard bereichsteiler*. Standardmäßige bereichsteiler ist verantwortlich für das Layout aller andockbare Bereiche der DockPosition. Die Dock-Manager verwaltet eine Liste der Standard-bereichsteiler und eine Liste von Bereichen. Dock-Manager sind für das Layout aller andockbare Bereiche verantwortlich.

## <a name="containers"></a>Container

Alle in der Größe veränderbaren Bereiche, wenn sich in der Dockingstation werden in Containern verwaltet. Container werden durch dargestellt die [CPaneContainer-Klasse](../mfc/reference/cpanecontainer-class.md). Jeder Container enthält Zeiger auf die Links, rechts, linken Untercontainer, richtigen untergeordneten Container und der Splitter zwischen dem linken und rechten teilen. (*Links* und *rechten* nicht auf physische Seiten verweisen, sondern vielmehr erkennen die Verzweigungen einer Baumstruktur.) Auf diese Weise kann eine Struktur von Bereichen und Aufteilungen erstellen und erzielen daher komplexe Layouts der Bereiche, die zusammen ein Größe geändert werden können. Die `CPaneContainer` Klasse verwaltet die Struktur von Containern, sichert auch zwei Listen mit Bereichen sowie mit den Schiebereglern, die in dieser Struktur befinden. Container-Manager im Bereich sind in der Regel in Standard-Schieberegler und Minirahmenfenster, die mehrere Bereiche enthalten eingebettet.

## <a name="auto-hide-control-bars"></a>Automatisches Ausblenden von Steuerleisten

Standardmäßig jede `CDockablePane` unterstützt das Feature für automatisches ausblenden. Wenn ein Benutzer klickt auf die Beschriftung der Schaltfläche "anheften" der `CDockablePane`, das Framework wechselt den Bereich zum Modus "automatisch ausblenden". Um den Klick behandeln zu können, erstellt das Framework eine [CMFCAutoHideBar-Klasse](../mfc/reference/cmfcautohidebar-class.md) und [CMFCAutoHideButton-Klasse](../mfc/reference/cmfcautohidebutton-class.md) zugeordneten der `CMFCAutoHideBar` Objekt. Das Framework legt die neue `CMFCAutoHideBar` auf die [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md). Das Framework fügt außerdem die `CMFCAutoHideButton` auf der Symbolleiste. Die [CDockingManager-Klasse](../mfc/reference/cdockingmanager-class.md) verwaltet die `CDockablePane`.

## <a name="tabbed-control-bars-and-outlook-bars"></a>Steuerleisten im Registerkartenformat und die Outlook-Balken

Die [CMFCBaseTabCtrl-Klasse](../mfc/reference/cmfcbasetabctrl-class.md) implementiert die Basisfunktionalität von einem Fenster im Registerkartenformat mit abtrennbaren Registerkarten. Verwenden einer `CMFCBaseTabCtrl` Objekt, das Initialisieren einer [CBaseTabbedPane-Klasse](../mfc/reference/cbasetabbedpane-class.md) in Ihrer Anwendung. `CBaseTabbedPane` stammt aus `CDockablePane` und verwaltet einen Zeiger auf eine `CMFCBaseTabCtrl` Objekt. Die `CBaseTabbedPane` ermöglicht Benutzern das Andocken und ändern Sie die Größe im Registerkartenformat Schiebeleisten-Steuerelemente. Verwendung [CDockablePane:: Attachtotabwnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) Schiebeleisten-Steuerelemente dynamisch zu erstellen, die im Registerkartenformat und angedockt sind.

Die Outlook-Leistensteuerelement basiert ebenfalls auf Registerkarten Balken. Die [CMFCOutlookBar-Klasse](../mfc/reference/cmfcoutlookbar-class.md) ergibt sich aus `CBaseTabbedPane`. Weitere Informationen zur Verwendung von Outlook-Leiste finden Sie unter [CMFCOutlookBar-Klasse](../mfc/reference/cmfcoutlookbar-class.md).

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)

