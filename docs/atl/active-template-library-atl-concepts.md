---
title: Active Template Library (ATL) Konzepte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5636f92df42116b838c24c21d81f0b320f7d69c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358113"
---
# <a name="active-template-library-atl-concepts"></a>ATL-Konzepte (Active Template Library)
Die Active Template Library (ATL) ist eine Reihe von Template-basierten C++-Klassen, mit die Sie kleine, schnelle Component Object Model (COM)-Objekte erstellen können. Er verfügt über spezielle Unterstützung für wichtige COM-Funktionen, einschließlich vordefinierte Implementierungen, duale Schnittstellen, standard-COM-Enumerator-Schnittstellen, Verbindungspunkte, abtrennbare Schnittstellen und ActiveX-Steuerelemente.  
  
 Wenn Sie einen hohen ATL-Programmierung erfordern, sollten Sie mehr Attribute, ein neues Feature in Visual C++ .NET vorgestellt, die zum Vereinfachen der COM-Programmierung entworfen wurde. Weitere Informationen finden Sie unter [der attributierten Programmierung](../windows/attributed-programming-concepts.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
 Führt Sie durch die Erstellung eines Steuerelements, und einige ATL-Grundlagen der Prozess veranschaulicht.  
  
 [Einführung in COM und ATL](../atl/introduction-to-com-and-atl.md)  
 Stellt die wichtigsten Konzepte hinter das Component Object Model (COM). Diesem Artikel wird auch kurz erläutert, was ATL ist und wenn Sie sie verwenden sollten.  
  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)  
 Erläutert die Beziehung zwischen verschiedenen ATL-Klassen und wie diese Klassen implementiert werden.  
  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)  
 Beschreibt die duale Schnittstellen aus Sicht der ATL.  
  
 [ATL-Auflistungen und -Enumeratoren](../atl/atl-collections-and-enumerators.md)  
 Beschreibt die Implementierung und die Erstellung von Auflistungen und-Enumerationen in ATL  
  
 [Grundlagen von zusammengesetzten Steuerelementen](../atl/atl-composite-control-fundamentals.md)  
 Bietet schrittweise Anleitungen zum Erstellen eines zusammengesetzten Steuerelements an. Ein zusammengesetztes Steuerelement ist ein ActiveX-Steuerelement, das andere ActiveX-Steuerelemente oder Windows-Steuerelemente enthalten kann.  
  
 [Fragen und Antworten zur ATL-Steuerelementkapselung](../atl/atl-control-containment-faq.md)  
 Behandelt die grundlegenden Fragen zum Hosten von Steuerelementen mit ATL  
  
 [ATL COM-Eigenschaftenseiten](../atl/atl-com-property-pages.md)  
 Veranschaulicht das Festlegen und Implementieren von COM-Eigenschaftenseiten.  
  
 [ATL-Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)  
 Stellt eine schrittweise Anleitung zum Erstellen eines DHTML-Steuerelements bereit.  
  
 [ATL-Verbindungspunkte](../atl/atl-connection-points.md)  
 Erläutert, was Verbindungspunkte sind und wie Sie ATL implementiert.  
  
 [Ereignisbehandlung und ATL](../atl/event-handling-and-atl.md)  
 Beschreibt die Schritte, die Sie ergreifen, um mithilfe des ATL-COM-Ereignisse behandeln müssen [IDispEventImpl](../atl/reference/idispeventimpl-class.md) und [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Klassen.  
  
 [ATL und der freethreaded Marshaller](../atl/atl-and-the-free-threaded-marshaler.md)  
 Stellt Informationen zu den ATL-Assistent für einfache Objekte des-Option, die Ihre Klasse der freethreaded Marshaller (FTM) aggregieren kann.  
  
 [Angeben des Threadingmodells des Projekts](../atl/specifying-the-threading-model-for-a-project-atl.md)  
 Beschreibt die Makros, die zur Steuerung der Laufzeit-Leistung im Zusammenhang mit threading in Ihrem Projekt verfügbar sind.  
  
 [ATL-Modulklassen](../atl/atl-module-classes.md)  
 Beschreibt die neuen Modulklassen für ATL 7.0. Modulklassen implementieren die grundlegende Funktionen von ATL  
  
 [ATL-Dienste](../atl/atl-services.md)  
 Behandelt die Abfolge von Ereignissen, die auftreten, wenn ein Dienst implementiert wird. Außerdem kommuniziert über einige der Konzepte im Zusammenhang mit der Entwicklung eines Diensts.  
  
 [ATL-Fensterklassen](../atl/atl-window-classes.md)  
 Beschreibt, wie zum Erstellen, übergeordnete Klasse und Unterklasse Fenstern in ATL ATL-Fensterklassen sind keine COM-Klassen.  
  
 [ATL-Auflistungsklassen](../atl/atl-collection-classes.md)  
 Beschreibt, wie Arrays und Karten in ATL  
  
 [Die ATL-Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)  
 Erläutert die ATL scripting Syntax und ersetzbare Parameter. Es wird das Einrichten einer statischen Verknüpfung auf die Registrierungsstelle erläutert.  
  
 [Programmieren mit ATL- und C-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)  
 Erläutert die Vorteile der statisch oder dynamisch zu C Run-Time Library (CRT) verknüpfen.  
  
 [Programmieren mit CComBSTR](../atl/programming-with-ccombstr-atl.md)  
 Erläutert verschiedene Situationen mit Vorsicht beim Programmieren mit `CComBSTR`.  
  
 [Codierungsreferenz](../atl/atl-encoding-reference.md)  
 Enthält Funktionen und Makros, die in einen Bereich von allgemeinen Internetstandards wie Uuencode Hexadezimal, und UTF8 bei atlenc.h unterstützen Codierung.  
  
 [Referenz zu Hilfsprogrammen](../atl/atl-utilities-reference.md)  
 Stellt Code zum Bearbeiten von Pfaden und URLs in Form von [CPathT](../atl/reference/cpatht-class.md) und [CUrl](../atl/reference/curl-class.md). Ein Threadpool [CThreadPool](../atl/reference/cthreadpool-class.md), in Ihren eigenen Anwendungen verwendet werden kann. Dieser Code kann in atlpath.h und atlutil.h gefunden werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ATL-Beispiele](../visual-cpp-samples.md)  
 Enthält Beschreibungen und Links zu ATL Beispielprogramme.  
  
 [Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md)  
 Enthält Informationen über ATL-Projekt-Assistenten.  
  
 [ATL-Steuerelement-Assistent](../atl/reference/atl-control-wizard.md)  
 Erläutert das Hinzufügen von Klassen.  
  
 [Attributiertes Programmieren](../windows/attributed-programming-concepts.md)  
 Bietet eine Übersicht zur Verwendung von Attributen zum COM-Programmierung sowie einer Liste mit Links zu ausführlicheren Themen zu vereinfachen.  
  
 [ATL-Klassenübersicht](../atl/atl-class-overview.md)  
 Bietet Referenzinformationen und Links zu den ATL-Klassen.

