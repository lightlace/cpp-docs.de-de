---
title: 'C++Buildeinblicke: Grundlagen zu Windows Performance Analyzer'
description: Tutorial zum Durchführen von grundlegenden Vorgängen in Windows Performance Analyzer.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4bd91698561175d876b7a3351a0ed6e85ef73a35
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633207"
---
# <a name="c-build-insights-windows-performance-analyzer-basics"></a>C++Buildeinblicke: Grundlagen zu Windows Performance Analyzer

::: moniker range="<=vs-2017"

Die C++ Build Insights-Tools sind in Visual Studio 2019 verfügbar. Um die Dokumentation für diese Version anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2019 fest.

::: moniker-end
::: moniker range="vs-2019"

Zum C++ effektiven Verwenden von Build Insights sind einige Kenntnisse der Windows Performance Analyzer (WPA) erforderlich. In diesem Artikel erfahren Sie, wie Sie gängige WPA-Vorgänge kennenlernen. Weitere Informationen zur Verwendung von WPA finden Sie in der Dokumentation zu [Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) .

## <a name="change-the-view-mode"></a>Ändern des Ansichtsmodus

WPA bietet zwei grundlegende Ansichtsmodi, mit denen Sie Ihre Ablauf Verfolgungen untersuchen können:

- Graph-Modus und
- Tabellen Modus.

Sie können zwischen diesen mithilfe der Symbole im Ansichtsmodus oben im Ansichts Bereich wechseln:

![Wechseln zwischen Graph-und Tabellen Modus.](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>Voreinstellungen auswählen

Die C++ meisten buildinsights WPA-Ansichten verfügen über mehrere Voreinstellungen, aus denen Sie auswählen können. Sie können die gewünschte Voreinstellung mithilfe des Dropdown Menüs am oberen Rand des Bereichs Ansicht auswählen:

![Auswählen einer Voreinstellung.](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>Vergrößern und verkleinern

Einige buildüberwachungen sind so groß, dass es schwierig ist, die Details herauszufinden. Um einen Bereich zu vergrößern, der Sie interessiert, klicken Sie mit der rechten Maustaste auf das Diagramm, und wählen Sie **Zoom**aus. Sie können jederzeit zur vorherigen Einstellung zurückkehren, indem Sie **Rückgängig vergrößern**auswählen. Diese Abbildung zeigt ein Beispiel für die Verwendung einer Auswahl und des **Zoom** -Befehls, um einen Abschnitt des Diagramms zu vergrößern:

![Vergrößern eines Diagramms.](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>Nach verschiedenen Spalten gruppieren

Sie können die Art und Weise anpassen, wie die Ablauf Verfolgung angezeigt wird. Klicken Sie am oberen Rand eines Ansichts Bereichs auf das Zahnrad Symbol, und ordnen Sie die Spalten im Build Explorer-Ansichts-Editor neu an. Die in diesem Dialogfeld über der gelben Zeile gefundenen Spalten sind die Spalten, nach denen Ihre Daten Zeilen gruppiert sind. Die Spalte rechts oberhalb der gelben Linie ist besonders: in der Diagramm Ansicht wird Sie auf den farbigen Balken angezeigt.

Diese Abbildung zeigt ein Beispiel eines Balkendiagramms für einen Link Aufruf. Verwenden Sie das Zahnrad Symbol, um das Dialogfeld Ansicht-Editor für Build-Explorer zu öffnen. Anschließend ziehen wir die Spalten Einträge für die Komponente und den Namen über die Gelbe Zeile. Die Konfiguration wird geändert, um den Detailgrad zu erhöhen und um zu sehen, was im Linker tatsächlich passiert ist:

![Vergrößern eines Diagramms.](media/wpa-grouping.gif)

## <a name="see-also"></a>Siehe auch

[Machen Sie sich C++ mit den Build Insights](get-started-with-cpp-build-insights.md) -\
[vcperf. exe-Referenz](vcperf-reference.md)\
[Referenz\ zu Windows Performance Analyzer-Sichten](wpa-views-reference.md)
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
