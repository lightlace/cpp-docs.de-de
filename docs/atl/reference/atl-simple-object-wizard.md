---
title: "ATL-Assistent für einfache Objekte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cbefa4a8036802599dd97f31d57f18204fd6104f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-simple-object-wizard"></a>ATL-Assistent für einfache Objekte
Dieser Assistent fügt dem Projekt ein minimales COM-Objekt. Mithilfe dieser Seite des Assistenten geben Sie die Namen, die die C++-Klasse und die Dateien für das Objekt und seine COM-Funktionalität zu identifizieren.  
  
 Verwenden der [Optionen](../../atl/reference/options-atl-simple-object-wizard.md) dieser Assistentenseite geben Sie das Objekt Threadingmodell und seine Aggregation zu unterstützen, und gibt an, ob duale Schnittstellen und die Automatisierung unterstützt. Sie können auch Unterstützung für die Informationen fehlerschnittstelle, Verbindungspunkte, Internet Explorer-Unterstützung und Freethread-Marshalling angeben.  
  
## <a name="remarks"></a>Hinweise  
 Ab Visual Studio 2008 können von diesem Assistenten erstellte Registrierungsskript registriert die COM-Komponenten unter **HKEY_CURRENT_USER** anstelle von **HKEY_LOCAL_MACHINE**. Um dieses Verhalten zu ändern, legen Sie die **Register-Komponente für alle Benutzer** des ATL-Assistenten die Option.  
  
## <a name="names"></a>Namen  
 Geben Sie die Namen für das Objekt, Schnittstelle und Klassen, die dem Projekt hinzugefügt werden. Mit Ausnahme von **Kurzname**, alle anderen Felder können unabhängig von den anderen bearbeitet werden. Wenn Sie den Text für ändern **Kurzname**, in den Namen von allen anderen Feldern auf dieser Seite wird die Änderung übernommen. Wenn Sie ändern die **Co-Klasse** Verzeichnisnamens COM-Abschnitt, die Änderung wirkt sich die **Typ** und **ProgID** Dialogfelder, aber die **Schnittstelle** Name wird nicht geändert. Dieses naming Verhalten wurde entworfen, um alle Namen leicht erkennbaren für Sie bereitzustellen bei der Entwicklung Ihrer Kontrolle.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Projekten bearbeitet werden. Wenn Ihr Projekt attributiert, können nicht bearbeitet **Coclass**.  
  
## <a name="c"></a>C++  
 Enthält Informationen für die C++-Klasse, die für das Objekt erstellt wurde.  
  
 **Kurzname**  
 Legt den abgekürzten Namen für das Objekt. Der Name, den Sie angeben, bestimmt die `Class` und **Co-Klasse** Namen, die **cpp-Datei** und **.h-Datei** Namen, die **Schnittstelle**Name, der **Typ** Namen, und die **ProgID**, es sei denn, diese Felder einzeln zu ändern.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **Klasse**  
 Legt den Namen der Klasse erstellt werden soll. Dieser Name wird auf Grundlage des Namens, die Sie gewähren **Kurzname**, "C", das Standard-Präfix für einen Klassennamen vorangestellt.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für das neue Objekt-Klasse. Standardmäßig basiert auf den Namen, die Sie gewähren dieser Name **Kurzname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht an den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Implementierung der Klasse mit dem Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **Mit Attributen versehen**  
 Gibt an, ob das Objekt Attribute verwendet. Wenn Sie ein Objekt zu einem attributierten ATL-Projekt hinzufügen, ist diese Option ausgewählt und nicht verfügbar, um zu ändern. D. h. können Sie nur attributierte Objekte zu einem Projekt mit Attribut-Unterstützung hinzufügen.  
  
 Sie können ein attributiertes Objekt nur ein ATL-Projekt hinzufügen, die Attribute verwendet. Wenn Sie diese Option für eine ATL-Projekt, die über keinen Attribut unterstützen auswählen, werden Sie vom Assistenten aufgefordert, anzugeben, ob die Attribut-Unterstützung zum Projekt hinzufügen möchten.  
  
 Standardmäßig werden alle Objekte, die Sie hinzufügen, nachdem Sie diese Option festlegen als attributiert festgelegt (das Kontrollkästchen ist aktiviert). Sie können deaktivieren Sie dieses Kontrollkästchen, um ein Objekt hinzuzufügen, das keine Attribute verwendet.  
  
 Finden Sie unter [Anwendungseinstellungen, ATL-Projektassistenten](../../atl/reference/application-settings-atl-project-wizard.md) und [grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md) für Weitere Informationen.  
  
## <a name="com"></a>COM  
 Enthält Informationen über die COM-Funktionalität für das Objekt.  
  
 **Co-Klasse**  
 Legt den Namen der Komponentenklasse, die eine Liste von Schnittstellen, die vom Objekt unterstützten enthält.  
  
> [!NOTE]
>  Wenn Sie das Projekt, das Verwenden von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass das Objekt Attribute verwendet, können Sie diese Option nicht ändern, da ATL nicht enthält die `coclass` Attribut.  
  
 **Type**  
 Legt die Beschreibung des Objekts, die in der Registrierung angezeigt wird  
  
 **Interface**  
 Legt die Schnittstelle, die Sie für Ihr Objekt zu erstellen. Diese Schnittstelle enthält die benutzerdefinierten Methoden.  
  
 **ProgID**  
 Legt den Namen, den Container, anstatt die CLSID des Objekts verwenden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Einfaches ATL-Objekt](../../atl/reference/adding-an-atl-simple-object.md)

