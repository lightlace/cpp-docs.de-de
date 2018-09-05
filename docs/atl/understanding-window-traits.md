---
title: ATL-Fenstermerkmale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ea30c79712ced6c86da0b030882fe6a88359ed
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764042"
---
# <a name="understanding-window-traits"></a>Einführung in Fenstermerkmale

Fenster "traits"-Klassen bieten eine einfache Methode für die Standardisierung der Stile, die für die Erstellung eines ATL-Fenster-Objekts verwendet. Fenster "traits" werden als Vorlagenparameter von akzeptiert [CWindowImpl](../atl/reference/cwindowimpl-class.md) und anderen ATL-Fensterklassen als eine Möglichkeit, Window-Stile auf Klassenebene bereitzustellen.

Wenn der Ersteller einer Instanz Fenster Stile explizit im Aufruf von nicht bereitstellt [erstellen](../atl/reference/cwindowimpl-class.md#create), Sie können eine "traits"-Klasse verwenden, um sicherzustellen, dass das Fenster immer noch mit den richtigen Formatvorlagen erstellt wird. Sie können auch sicher, dass für bestimmte Formate für alle Instanzen dieser Fensterklasse zugleich andere Stile auf einer Basis pro Instanz festgelegt werden.

## <a name="atl-window-traits-templates"></a>ATL-Fenster "traits"-Vorlagen

ATL bietet zwei Fenster "traits"-Vorlagen, mit die Sie Standardstile zum Zeitpunkt der Kompilierung mit ihren Vorlagenparametern festlegen können.

|Klasse|Beschreibung|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|Verwenden Sie diese Vorlage, wenn Sie möchten, um Standardwert Window-Stile anzugeben, die verwendet werden, wenn keine anderen Arten im Aufruf angegeben werden `Create`. Kompilierzeit für die Stile, die angegebene Laufzeit haben Vorrang vor über die Formatvorlagen auf festgelegt.|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Verwenden Sie diese Klasse, wenn Sie möchten Stile an, die stets für Window-Klasse festgelegt werden muss. Die Stile, die zur Laufzeit bereitgestellt werden mit den Stilen, legen Sie zum Zeitpunkt der Kompilierung mit dem bitweisen OR-Operator kombiniert.|

Neben diesen Vorlagen können-ATL bietet eine Reihe von vordefinierten spezialisierungen der `CWinTraits` Vorlagen für häufig verwendeten Kombinationen von Window-Stile. Finden Sie unter den [CWinTraits](../atl/reference/cwintraits-class.md) Referenzdokumentation für die vollständigen Details.

## <a name="custom-window-traits"></a>Benutzerdefinierte Fenstermerkmale

In dem unwahrscheinlichen Fall, dass spezialisierenden eine der Vorlagen aus, von ATL reicht nicht aus und müssen Sie Ihre eigenen "traits"-Klasse zu erstellen, müssen Sie nur eine Klasse erstellen, die zwei statische Funktionen implementiert: `GetWndStyle` und `GetWndStyleEx`:

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

Jede dieser Funktionen wird ein Style-Wert zur Laufzeit übergeben die sie verwenden können, um einen neuen Style-Wert zu erzeugen. Wenn Ihr Fenster "traits"-Klasse als Vorlagenargument für eine ATL-Fensterklasse verwendet wird, die Style-Werte, die für diese statische Funktionen übergeben werden alle als die Style-Argumente, die übergeben wurde [erstellen](../atl/reference/cwindowimpl-class.md#create).

## <a name="see-also"></a>Siehe auch

[Fensterklassen](../atl/atl-window-classes.md)

