---
title: Befehlszeilenwarnung D9025
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: e7090dda72868ad7ee4d5f8e4f1ba6a0ad121c98
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822462"
---
# <a name="command-line-warning-d9025"></a>Befehlszeilenwarnung D9025

Überschreiben von 'option1' mit 'option2'

Die *option1* Option angegeben wurde, aber durch überschrieben *option2*. Die *option2* Option wurde verwendet.

Wenn zwei Optionen zur Verfügung, widersprüchliche oder inkompatible Direktiven angeben, wird die Direktive angegeben Sie ausdrücklich oder konkludent, in der Option-Visual auf der rechten Seite in der Befehlszeile verwendet.

Wenn Sie diese Warnung zu erhalten, beim Kompilieren von der Entwicklungsumgebung aus, und nicht sicher sind, in denen die in Konflikt stehenden Optionen stammen, berücksichtigen Sie Folgendes:

- Eine Option kann entweder im Code oder in den projekteinstellungen des Projekts angegeben werden. Bei Betrachtung des Compilers [Eigenschaftenseiten Befehlszeile](../../build/reference/command-line-property-pages.md) und wenn Sie sehen, dass die in Konflikt stehenden Optionen in der **alle Optionen** Feld, und klicken Sie dann die Optionen in den Eigenschaftenseiten des Projekts, andernfalls die Optionen festgelegt sind im Quellcode werden festgelegt werden.

   Wenn die Optionen in den Eigenschaftenseiten des Projekts festgelegt werden, suchen Sie auf den Compiler-Präprozessor-Eigenschaftenseite (mit den Projektknoten im Projektmappen-Explorer ausgewählt).  Wenn Sie nicht angezeigt, werden die Option festgelegt, die Einstellungen für die Präprozessor Eigenschaftenseiten für jede Quellcodedatei (im Projektmappen-Explorer) stellen Sie sicher, ist es nicht es hinzugefügt.

   Wenn die Optionen im Code festgelegt sind, konnte es entweder im Code oder in der Windows-Header festgelegt werden.  Sie könnten versuchen, eine vorverarbeitete Datei erstellen ([/p](../../build/reference/p-preprocess-to-a-file.md)), und suchen sie für das Symbol.