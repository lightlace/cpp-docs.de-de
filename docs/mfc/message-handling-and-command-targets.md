---
title: "Meldungsbehandlung und Befehlsziele"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsrouting, Befehlsziele"
  - "Befehlsziele"
  - "IOleCommandTarget-Schnittstelle"
  - "Meldungsbehandlung, Aktive Dokumente"
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Meldungsbehandlung und Befehlsziele
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Befehlsdispatchschnittstelle `IOleCommandTarget` definiert einen einfachen und erweiterbaren Mechanismus, Befehle abzufragen und auszuführen.  Dieser Mechanismus ist einfacher als `IDispatch` der Automatisierung, da er vollständig auf einen Standardsatz von Befehlen verwendet; Befehle erfüllen selten und Argumente keine Typinformationen werden beteiligt \(Typsicherheit wird für beispielsweise auch verringert\).  
  
 Im Befehlsdispatchschnittstellenentwurf gehört jeder Befehl einer "Befehlsgruppe" die auch mit **Guid** identifiziert wird.  Daher kann jeder eine neue Gruppe definieren und alle Befehle in dieser Gruppe ohne eine Anforderung definieren, mit Microsoft oder jedem anderen Lieferanten zu koordinieren. \(Dies steht im Grunde dieselbe Weise der Definition wie **dispinterface** und **dispIDs** in der Automatisierung.  Es gibt Überlappung hier, obwohl dieser Befehlsroutingmechanismus nur für Befehlsrouting und nicht für die Skripterstellung\/Programmierbarkeit meist Kontext als Automatisierungshandles ist.\)  
  
 `IOleCommandTarget` behandelt die folgenden Szenarien:  
  
-   Wenn ein Objekt direkt aktiviert ist, werden nur die Symbolleisten des Objekts werden in der Regel angezeigt und die Symbolleisten möglicherweise des Objekts haben Schaltflächen für einige der Containerbefehle wie **Drucken**, **Drucken**`New`,**Vorschau**, **Speichern**, **Zoom** und andere. \(Standardeinstellungen der direkte Aktivierung wird empfohlen, dass Objekte entfernen, solche Schaltflächen von ihren Symbolleisten oder deaktivieren diese mindestens.  Dieser Entwurf ermöglicht diese Befehle aktiviert werden bei dem richtigen Handler weitergeleitet werden.\) Derzeit gibt es keinen Mechanismus, damit das Objekt die Befehle dem Container ausliefert.  
  
-   Wenn ein aktives Dokument auf einem Active Document\-Container \(wie sollte\) eingebettet ist, muss der Container solches Befehle **Drucken**, **Seite Setup**, **Eigenschaften** und andere auf das aufnehmende aktiven Dokument senden.  
  
 Das Routing des einfachen Befehls kann über vorhandene Automatisierungsstandards \- und `IDispatch` behandelt werden.  Allerdings ist der Verarbeitungsaufwand, der in `IDispatch` ausgeführt wird, mehr als erforderlich, hier ist, daher stellt `IOleCommandTarget` das einfachere Möglichkeit, z Zwecke zu erfüllen:  
  
 `interface IOleCommandTarget : IUnknown`  
  
 `{`  
  
 `HRESULT QueryStatus(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] ULONG cCmds,`  
  
 `[in,out][size_is(cCmds)] OLECMD *prgCmds,`  
  
 `[in,out] OLECMDTEXT *pCmdText);`  
  
 `HRESULT Exec(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] DWORD nCmdID,`  
  
 `[in] DWORD nCmdExecOpt,`  
  
 `[in] VARIANTARG *pvaIn,`  
  
 `[in,out] VARIANTARG *pvaOut);`  
  
 `}`  
  
 Die `QueryStatus`\-Methode hier testet, ob eine bestimmte, die aus Befehlen, die Gruppe identifiziert wird mit **Guid** festgelegt ist, unterstützt wird.  Dieser Aufruf füllt ein Array **OLECMD**\-Werte \(Strukturen\) unterstützten mit der Liste der Befehle aus und gibt den Text zurück, der den Namen eines Befehls und\/oder der Statusinformationen beschreibt.  Wenn der Aufrufer ein Befehl aufgerufen möchte, kann es den Befehl und Set \( **Guid**\) für **Exec** zusammen mit den Optionen und Argumente übergeben und anschließend abgerufen ein Rückgabewert.  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containers.md)