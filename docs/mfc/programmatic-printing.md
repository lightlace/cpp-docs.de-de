---
title: "Programmgesteuertes Drucken"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Aktive Dokumente [C++], Drucken"
  - "IPrint-Schnittstelle"
  - "Drucken [MFC]"
  - "Drucken [MFC], Aktive Dokumente"
  - "Drucken [MFC], programmatisch"
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Programmgesteuertes Drucken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE kann die Möglichkeit permanente, um Dokumente \(**GetClassFile**\) eindeutig zu identifizieren und sie in ihren zugeordneten Code \(`CoCreateInstance`, **QueryInterface\(IID\_IPersistFile\)**, **QueryInterface\(IID\_IPersistStorage\)**, **IPersistFile::Load** und **IPersistStorage::Load**\) zu laden.  Um Druckdokumente weiter zu aktivieren, stellt Active Document\-Einschluss \(mithilfe eines vorhandenen OLE\-Entwurfs ursprünglich enthalten nicht mit OLE 2.0\) eine BasisStandarddruckschnittstelle, `IPrint`, im Allgemeinen verfügbar gemacht wird jedes Objekt vor das persistenten Zustand des Dokumenttyps laden kann.  Jede Ansicht eines aktiven Dokuments kann die **IPrint** \-Schnittstelle optional unterstützen, um diese Funktionen bereitzustellen.  
  
 Die `IPrint`\-Schnittstelle wird definiert, wie folgt:  
  
 `interface IPrint : IUnknown`  
  
 `{`  
  
 `HRESULT SetInitialPageNum([in] LONG nFirstPage);`  
  
 `HRESULT GetPageInfo(`  
  
 `[out] LONG *pnFirstPage,`  
  
 `[out] LONG *pcPages);`  
  
 `HRESULT Print(`  
  
 `[in] DWORD grfFlags,`  
  
 `[in,out] DVTARGETDEVICE **pptd,`  
  
 `[in,out] PAGESET ** ppPageSet,`  
  
 `[in,out] STGMEDIUM **ppstgmOptions,`  
  
 `[in] IContinueCallback* pCallback,`  
  
 `[in] LONG nFirstPage,`  
  
 `[out] LONG *pcPagesPrinted,`  
  
 `[out] LONG *pnPageLast);`  
  
 `};`  
  
 Client\- und Containereinfach Verwendung von **IPrint::Print**, das Dokument anzuweisen, um sich einmal zu drucken, dass das Dokument geladen wird und Drucksteuerflags, das Zielgerät, Seiten angibt, und die zu druckenden zusätzliche Optionen.  Der Client kann die Fortsetzung des Druckens über die Schnittstelle `IContinueCallback` festlegen \(siehe unten\).  
  
 Außerdem unterstützt  **IPrint::SetInitialPageNum** die Fähigkeit, eine Reihe Dokumente zu drucken, während eines, indem nahtlos Seiten nummeriert, sorgfältig ein Vorteil für Active Document\-Container sollte wie.  **IPrint::GetPageInfo**, Paginierungsinformationen für einfach, indem dem Aufrufer zulässt, um die Dateien abzurufen Seitenzahl, die zuvor an **SetInitialPageNum** übergeben wird \(oder den internen Standardeinstellung des Dokuments, der Seitenzahl starten\) und zur Anzahl vonseiten im Dokument.  
  
 Objekte, die `IPrint` unterstützen, werden in der Registrierung mit der "druckbaren" Schlüssel markiert, die unter CLSID des Objekts gespeichert wird:  
  
 HKEY\_CLASSES\_ROOT\\CLSID\\{...}\\Printable  
  
 `IPrint` ist normalerweise auf demselben Objekt implementiert, das entweder `IPersistFile` oder `IPersistStorage` unterstützt.  Aufrufer sollten die Funktionen, die einen beständigen Zustand von einer Klasse programmgesteuert zu drucken, indem in der Registrierung nach der "druckbaren" Schlüssel finden.  Derzeit "druckbare" gibt Unterstützung für mindestens `IPrint`; andere Schnittstellen werden in Zukunft definiert sein, die von `QueryInterface` verfügbar sind, in dem für das **IPrint**  einfach der Unterstützung darstellt.  
  
 Während einer Druckprozedur sollten Sie den Client bzw., dass der Container den Druckvorgang initiierten, um zu steuern, ob der Druck fortgesetzt werden soll.  Beispielsweise unterstützt möglicherweise der Container einen "STOPP\- DRUCK" Befehl, der den Druckauftrag so schnell wie möglich beendet werden soll.  Um diese Funktion zu unterstützen, kann der Client eines druckbaren Objekts ein kleines Benachrichtigungssenkenobjekt mit der `IContinueCallback`\- Schnittstelle implementieren:  
  
 `interface IContinueCallback : IUnknown`  
  
 `{`  
  
 `HRESULT FContinue(void);`  
  
 `HRESULT FContinuePrinting(`  
  
 `[in] LONG cPagesPrinted,`  
  
 `[in] LONG nCurrentPage,`  
  
 `[in] LPOLESTR pszPrintStatus);`  
  
 `};`  
  
 Diese Schnittstelle soll, um als generische Fortsetzungsrückruffunktion hilfreich, die verschiedenen Fortsetzungsprozeduren in der Win32\-API stattfindet \(wie **AbortProc** für Druck und **EnumMetafileProc** für Metadateienumeration\).  Daher ist dieser Schnittstellenentwurf in einer Vielzahl von aufwändigen empfohlen nützlich.  
  
 In die generischsten Fällen wird die Funktion **IContinueCallback::FContinue** in regelmäßigen Abständen von jedem Prozess längeren aufgerufen.  Das Senkenobjekt gibt `S_OK` zurück, um den Vorgang fortzusetzen und **S\_FALSE**, um die Prozedur so schnell wie möglich beendet.  
  
 **FContinue** wird jedoch nicht im Kontext **IPrint::Print** verwendet; anstelle von **IContinueCallback::FContinuePrint** das Drucken.  Jedes Druckobjekt sollte **FContinuePrinting** in regelmäßigen Abständen aufrufen, das die Anzahl vonseiten, übergibt, die gedruckt haben, die Seitenzahl, die gedruckt werden, und eine weitere Zeichenfolge, die den Druckstatus beschreibt, der den Client möglicherweise verwendet, die dem Benutzer angezeigt \(z "Seite 5 aus 19 "\).  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containers.md)