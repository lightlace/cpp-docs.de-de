---
title: Überschreiben einer virtuellen Funktion
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: 9bb3fd34bbfa14cce1595ed586c4e1b66518e7b7
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694022"
---
# <a name="override-a-virtual-function"></a>Überschreiben einer virtuellen Funktion

Sie können virtuelle Funktionen überschreiben, die in einer Basisklasse des [Eigenschaftenfensters](/visualstudio/ide/reference/properties-window) von Visual Studio definiert sind.

**So überschreiben Sie eine virtuelle Funktion im Eigenschaftenfenster:**

1. Klicken Sie in der Klassenansicht auf die Klasse.

1. Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Überschreibungen**.

   > [!NOTE]
   > Die Schaltfläche **Überschreibungen** ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht auswählen oder in das Quellcodefenster klicken.

   In der linken Spalte werden die virtuellen Funktionen aufgelistet. Wenn der Name einer virtuellen Funktion auch in der rechten Spalte angezeigt wird, wurde bereits eine Überschreibung implementiert.

1. Wenn die Funktion über keine Überschreibung verfügt, klicken Sie auf die Zelle in der rechten Spalte des Eigenschaftenfensters, um den empfohlenen Namen der Funktionsüberschreibung als \<add>*FuncName* anzuzeigen.

1. Klicken Sie auf den empfohlenen Namen, um Stubcode für die Funktion hinzuzufügen.

1. Führen Sie zum Bearbeiten einer überschreibenden Funktion einen Doppelklick auf den Namen der Funktion in der Klassenansicht aus, und bearbeiten Sie den Code im Quellcodefenster.

Klicken Sie zum Entfernen einer Überschreibung auf den Namen der Überschreibungsfunktion in der rechten Spalte, und klicken Sie auf \<delete>*FuncName*. Der Code der Funktion wird auskommentiert.
