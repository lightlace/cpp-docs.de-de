---
title: Meldungsbehandlung und Befehlsziele | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- command targets [MFC]
- message handling [MFC], active documents
- IOleCommandTarget interface [MFC]
- command routing [MFC], command targets
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc0f00e4f660036e73e96d4beb999d37453bdf26
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929355"
---
# <a name="message-handling-and-command-targets"></a>Meldungsbehandlung und Befehlsziele
Die Dispatch-Befehlsschnittstelle `IOleCommandTarget` definiert einen einfachen und erweiterbaren Mechanismus zum Abfragen und Befehle ausführen. Dieser Mechanismus ist einfacher als das Automation `IDispatch` daran, dass es einen Standardsatz von Befehlen; vollständig benötigt Befehle sind selten, Argumente und keine Typinformationen beteiligt ist (typsicherheit wird für die Befehlsargumente ebenfalls verringert).  
  
 In den Entwurf der Befehl Dispatch-Schnittstelle, jeden Befehl gehört zu einer "Befehlsgruppe" die selbst, deren ermittelt wird eine **GUID**. Jeder kann daher, definieren Sie eine neue Gruppe und alle Befehle innerhalb dieser Gruppe, ohne die Notwendigkeit zur Koordinierung mit Microsoft oder einem anderen Hersteller zu definieren. (Dies ist im Wesentlichen die gleichen bedeutet, dass der Definition als eine **Dispinterface** plus **DispIDs** in Automation. Besteht überlappen, obwohl dieser Befehl Weiterleitungsmechanismus nur für Befehlsrouting und nicht für scripting/Programmierbarkeit in großem Umfang als Automation Handles ist.)  
  
 `IOleCommandTarget` behandelt die folgenden Szenarien:  
  
-   Wenn ein Objekt ist direktes aktiviert, nur das Objekt Symbolleisten in der Regel angezeigt sind und das Objekt Symbolleisten möglicherweise Schaltflächen für einige der containerbefehle wie **Drucken**, **Seitenansicht**,  **Speichern Sie**, **neu**, **Zoom**, und andere. (Direkte Aktivierung Standards wird empfohlen, die Objekte entfernen deaktivieren Sie solche Schaltflächen aus ihren Symbolleisten oder auf mindestens diese. Dieser Entwurf ermöglicht dieser Befehle zu aktiviert und noch an den richtigen Handler weitergeleitet werden.) Es gibt derzeit keinen Mechanismus für das Objekt, das diese Befehle auf den Container zu verteilen.  
  
-   Wenn ein aktiven Dokuments in einer active Document-Container (z. B. Office Binder) eingebettet ist, der Container müssen u. u. eine solche Senden von Befehlen **Drucken**, **Seiteneinrichtung**, **Eigenschaften**, und andere enthaltenen aktiven Dokument.  
  
 Dieses einfache Befehlsrouting über vorhandene Automation-Standards verarbeitet werden konnte und `IDispatch`. Allerdings den Aufwand mit `IDispatch` ist mehr als die hier erforderlichen wird damit `IOleCommandTarget` bietet eine einfachere Möglichkeit zum Ende der gleichen zu erreichen:  
  
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
  
 Die `QueryStatus` Methode an dieser Stelle testet, ob eine bestimmte Reihe von Befehlen, die mit identifiziert wird eine **GUID**, wird unterstützt. Dieser Aufruf füllt ein Array von **OLECMD** Werte (Strukturen) mit der Liste der unterstützten Befehle sowie das Zurückgeben von Text, der den Namen von einem Befehl und/oder Statusinformationen-Informationen beschreibt. Beim Aufrufen eines Befehls ist der Aufrufer möchte, können sie den Befehl übergeben (und die Gruppe **GUID**) zu `Exec` zusammen mit Optionen und Argumente, wieder einen Rückgabewert abrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containers.md)

