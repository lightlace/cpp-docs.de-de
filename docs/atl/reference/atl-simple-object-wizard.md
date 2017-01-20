---
title: "ATL-Assistent f&#252;r einfache Objekte"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.simple.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Objekten"
  - "ATL-Assistent für einfache Objekte"
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Assistent f&#252;r einfache Objekte
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einfügungen dieses Assistenten in das Projekt ein minimales COM\-Objekt.  Verwenden Sie diese Seite des Assistenten, um die Namen anzugeben, die die C\+\+\-Klasse und Dateien für das Objekt und seine COM\-Funktionalität identifizieren.  
  
 Verwenden Sie die [Optionen](../../atl/reference/options-atl-simple-object-wizard.md) Seite dieses Assistenten, um das Threadingmodell des Objekts anzugeben, die Aggregationsunterstützung und ob es duale Schnittstellen und Automatisierung unterstützt.  Sie können Unterstützung für die Fehlerinformationsschnittstelle, die Verbindungspunkte, die Internet Explorer\-Unterstützung und das Freethreadmarshalling auch angeben.  
  
## Hinweise  
 Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], registriert das Registrierungsskript, das von diesem Assistenten erzeugt wird, die COM\-Komponenten unter **HKEY\_CURRENT\_USER** anstelle **HKEY\_LOCAL\_MACHINE**.  Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL\-Assistenten fest.  
  
## Namen  
 Geben Sie die Namen an, sodass das Objekt die Schnittstelle, die die Klassen und dem Projekt hinzugefügt werden können.  Neben **Kurzer Name** können alle anderen Felder unabhängig von anderen bearbeitet werden.  Wenn Sie den Text für **Kurzer Name** ändern, wird die Änderung in den Namen aller anderen Felder auf dieser Seite wiedergegeben.  Wenn Sie den **Coclass** Namen im COM\-Abschnitt ändern, wird die Änderung in den **Typ** und **ProgID** Feldern widerspiegelt, aber der **Schnittstelle** Name nicht geändert.  Dies Benennungsverhalten ist so konzipiert, dass alle Namen leichter identifizierbar für Sie zu vereinfachen, während Sie das Steuerelement entwickeln.  
  
> [!NOTE]
>  **Coclass** ist nur auf nicht attributierten Projekten bearbeitbar.  Wenn das Projekt zugeschriebenes, Sie **Coclass** nicht bearbeiten kann.  
  
## C\+\+  
 Stellt Informationen für die C\+\+\-Klasse bereit, die für das Objekt erstellt wird.  
  
 **Kurzer Name**  
 Legt den abgekürzten Namen für das Objekt fest.  Der Name, den Sie bereitstellen, bestimmt die `Class` und **Coclass** Namen, die **CPP\-Datei** und **H\-Datei** Namen, den **Schnittstelle** Namen, die **Typ** Namen und **ProgID**, es sei denn, Sie diese Felder einzeln ändern.  
  
 **H\-Datei**  
 Legt den Namen der Headerdatei für den neuen Objekts fest.  Standardmäßig lautet dieser Name auf dem Namen, den Sie in **Kurzer Name** bereitstellen.  Klicken Sie auf die Schaltfläche mit den Auslassungszeichen, um den Dateinamen auf den Speicherort der Auswahl zu speichern, oder die Klassendeklaration zu einer vorhandenen Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird der Assistent diese nicht an den ausgewählten Speicherort, bis Sie auf **Fertig stellen** im Assistenten auf klicken.  
  
 Der Assistent überschreibt keine Datei.  Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf klicken **Fertig stellen**, fordert Sie der Assistent auf, anzugeben, ob die Klassendeklaration den Inhalt der Datei angefügt werden soll.  **Ja** auf, um die Datei anzufügen, klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Klasse**  
 Legt den Namen der zu erstellenden Klasse, fest.  Dieser Name basiert auf den Namen, den Sie in **Kurzer Name** bereitstellen, vorangestellt von "C", das typische Präfix für einen Klassennamen.  
  
 **CPP\-Datei**  
 Legt den Namen der Implementierungsdatei für den neuen Objekts fest.  Standardmäßig lautet dieser Name auf dem Namen, den Sie in **Kurzer Name** bereitstellen.  Klicken Sie auf die Schaltfläche mit den Auslassungszeichen, um den Dateinamen auf den Speicherort der Auswahl zu speichern.  Die Datei wird nicht in den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten auf klicken.  
  
 Der Assistent überschreibt keine Datei.  Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf klicken **Fertig stellen**, fordert Sie der Assistent auf, anzugeben, ob die Klassenimplementierung den Inhalt der Datei angefügt werden soll.  **Ja** auf, um die Datei anzufügen, klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Attributiert**  
 Gibt an, ob das Objekt Attribute verwendet werden.  Wenn Sie ein Objekt auf einem attributierten ATL\-Projekt hinzufügen, wird diese Option und nicht verfügbar zu ändern ausgewählt.  Das heißt, Sie können nur attributierte Objekte zu einem Projekt hinzufügen, das mit Attributunterstützung erstellt wird.  
  
 Sie können ein attributiertes Objekt nur zu einem ATL\-Projekt hinzufügen, das Attribute verwendet werden.  Wenn Sie diese Option für ein ATL\-Projekt auswählen, das nicht Attributunterstützung verfügt, fordert Sie der Assistent auf, anzugeben, ob Sie Attributunterstützung zum Projekt hinzufügen möchten.  
  
 Standardmäßig Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributiertes festgelegt sind \(das Kontrollkästchen aktiviert\).  Sie können dieses Feld löschen, um ein Objekt hinzuzufügen, das nicht Attribute verwendet werden.  
  
 Siehe [Anwendungseinstellungen, ATL\-Projekt\-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [Grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) weitere Informationen.  
  
## COM  
 Stellt Informationen über die COM\-Funktionalität für das Objekt bereit.  
  
 **Coclass**  
 Legt den Namen der Komponentenklasse fest, die eine Liste der Schnittstellen enthält, die vom Objekt unterstützt werden.  
  
> [!NOTE]
>  Wenn Sie das Projekt mithilfe der Attribute erstellen oder, wenn Sie auf dieser Seite angeben, dass das Objekt Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht das `coclass`\-Attribut enthält.  
  
 **Typ**  
 Legt die Objektbeschreibung fest, in der Registrierung wird  
  
 **Schnittstelle**  
 Legt die Schnittstelle fest, die Sie für das Objekt erstellen.  Diese Schnittstelle enthält die benutzerdefinierten Methoden.  
  
 **ProgID**  
 Legt den Namen fest, den Container anstelle der CLSID des Objekts verwenden können.  
  
## Siehe auch  
 [ATL Simple Object](../../atl/reference/adding-an-atl-simple-object.md)