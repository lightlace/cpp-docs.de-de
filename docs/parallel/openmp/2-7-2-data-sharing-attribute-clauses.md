---
title: 2.7.2 Datenfreigabe-Attributklauseln | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecc6efac6e3d7356e51dc0ec57009ca9e5a71890
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 Datenfreigabe-Attributklauseln
Mehrere Anweisungen akzeptieren Klauseln, die einem Benutzer ermöglichen, die Freigabe Attribute von Variablen für die Dauer des Bereichs zu steuern. Freigeben von Attribut-Klauseln gelten nur für Variablen im lexikalischen Block der Richtlinie auf dem die-Klausel wird angezeigt. Nicht alle der folgenden Klauseln sind für alle Anweisungen zulässig. Die Liste der Klauseln, die für eine bestimmte Richtlinie gültig sind, werden mit der Direktive beschrieben.  
  
 Wenn eine Variable ist sichtbar, wenn eine parallele oder Arbeit-Freigabe-Konstrukt festgestellt wird, und die Variable in einer Freigabe Attribut-Klausel nicht angegeben ist oder **Threadprivate** Richtlinie, klicken Sie dann die Variable ist freigegeben. Statische Variablen, die in der dynamischen Wertebereich eines parallelen Bereichs deklariert werden, gemeinsam genutzt. Heap reservierter Speicher (z. B. **malloc()** in C oder C++ oder **neue** -Operator in C++) freigegeben wird. (Der Zeiger auf diesen Speicher jedoch entweder private oder freigegebene möglich.) Variablen mit automatischer Speicherdauer innerhalb der dynamischen Wertebereich eines parallelen Bereichs deklariert sind privat.  
  
 Die meisten Klauseln akzeptieren ein *Variablenliste* Argument, das eine durch Trennzeichen getrennte Liste der Variablen ist, die sichtbar sind. Wenn eine Variable in verwiesen Datenfreigabeklausel im Attribut weist einen Typ, der aus einer Vorlage abgeleitet und es sind keine weiteren Verweise auf Variablen im Programm, das Verhalten nicht definiert ist.  
  
 Alle Variablen, die innerhalb der Direktivenklauseln angezeigt werden, müssen sichtbar sein. Klauseln nach Bedarf wiederholt werden, aber keine Variable kann in mehr als eine Klausel angegeben werden, außer dass eine Variable in beiden angegeben werden, kann eine **Firstprivate** und ein **Lastprivate** Klausel.  
  
 Die folgenden Abschnitte beschreiben die Attribut-Klauseln mit Datenfreigabe:  
  
-   **private**, [Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf der Seite "25".  
  
-   **Firstprivate**, [Abschnitt 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) auf Seite 26.  
  
-   **Lastprivate**, [Abschnitt 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) Seite 27.  
  
-   **freigegebene**, [Abschnitt 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) Seite 27.  
  
-   **standardmäßige**, [Abschnitt 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) auf Seite 28.  
  
-   **Reduzierung der**, [Abschnitt 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) auf Seite 28.  
  
-   **Copyin**, [Abschnitt 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) auf der Seite "31".  
  
-   **Copyprivate**, [Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf der Seite "32".