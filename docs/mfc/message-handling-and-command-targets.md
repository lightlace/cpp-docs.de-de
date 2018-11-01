---
title: Meldungsbehandlung und Befehlsziele
ms.date: 11/04/2016
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
ms.openlocfilehash: f9212e32605a1fed179c931d4f63833e17870b5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442535"
---
# <a name="message-handling-and-command-targets"></a>Meldungsbehandlung und Befehlsziele

Die Dispatch-Befehlsschnittstelle `IOleCommandTarget` definiert einen einfachen und erweiterbaren Mechanismus zum Abfragen und Befehle ausführen. Dieser Mechanismus ist einfacher als das Automation `IDispatch` da vollständig einen Standardsatz von Befehlen verwendet; Befehle müssen Sie nur selten Argumente und keine Typinformationen beteiligt ist (die typsicherheit wird auch die Befehlsargumente verringert).

In dem Design der Dispatchschnittstelle, jeden Befehl gehört zu einer "Befehlsgruppe" das selbst mit gekennzeichnet ist eine **GUID**. Jeder kann aus diesem Grund definieren Sie eine neue Gruppe und alle Befehle in dieser Gruppe, ohne dass die Notwendigkeit zur Koordinierung mit Microsoft oder einem anderen Hersteller zu definieren. (Dies ist im Wesentlichen die gleiche Art und Weise der Definition als eine **Dispinterface** plus **DispIDs** in Automation. Es gibt hier überlappen zwar dieser Befehl Weiterleitungsmechanismus nur für das Befehlsrouting und nicht für die Skripterstellung/Programmierbarkeit in großem Umfang als Automation Handles.)

`IOleCommandTarget` behandelt die folgenden Szenarien:

- Wenn ein Objekt direkt aktiviert werden, nur des Objekts Symbolleisten sind in der Regel angezeigt, und des Objekts Symbolleisten möglicherweise Schaltflächen für einige der containerbefehle wie ist **Drucken**, **Seitenansicht**,  **Speichern Sie**, **neu**, **Zoom**, und andere. (Direkte Aktivierung Standards wird empfohlen, in der Objekte entfernen deaktiviert diese Schaltflächen über ihre Symbolleisten oder an mindestens werden. Dieser Entwurf ermöglicht diese Befehle aktiviert und noch an den richtigen Handler weitergeleitet werden.) Es gibt derzeit keinen Mechanismus für das Objekt, das diese Befehle aus, um den Container zu verteilen.

- Wenn ein aktiven Dokuments in einer active Document-Container (z. B. Office Binder) eingebettet ist, der Container müssen solche Senden von Befehlen **Drucken**, **Seiteneinrichtung**, **Eigenschaften**, und anderen für das enthaltene aktive Dokument.

Dieses einfache Befehlsrouting über vorhandene Automation-Standards verarbeitet werden konnte und `IDispatch`. Jedoch der Aufwand im Zusammenhang mit `IDispatch` ist mehr als notwendig, damit `IOleCommandTarget` bietet eine einfachere Möglichkeit, die die gleichen enden zu erreichen:

```
interface IOleCommandTarget : IUnknown
    {
    HRESULT QueryStatus(
        [in] GUID *pguidCmdGroup,
        [in] ULONG cCmds,
        [in,out][size_is(cCmds)] OLECMD *prgCmds,
        [in,out] OLECMDTEXT *pCmdText);
    HRESULT Exec(
        [in] GUID *pguidCmdGroup,
        [in] DWORD nCmdID,
        [in] DWORD nCmdExecOpt,
        [in] VARIANTARG *pvaIn,
        [in,out] VARIANTARG *pvaOut);
    }
```

Die `QueryStatus` Methode an dieser Stelle überprüft, ob eine bestimmte Reihe von Befehlen, die der Satz mit identifiziert wird eine **GUID**, wird unterstützt. Dieser Aufruf füllt ein Array von **OLECMD** Werte (Strukturen) mit der Liste der unterstützten Befehle sowie das Zurückgeben von Text, der den Namen der einen Befehl und/oder Statusinformationen Informationen beschreibt. Wenn der Aufrufer einen Befehl aufzurufen möchte, können sie den Befehl übergeben (und die Gruppe **GUID**) zu `Exec` zusammen mit Optionen und Argumente, Rückkehr einen Wert zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containers.md)

