---
title: 'TN032: MFC-Ausnahmemechanismus | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aee8ce02af874e1c3c30243a35e8f36acfce63f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414757"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC-Ausnahmemechanismus

Standard C++-Ausnahmemechanismus wurde von frühere Versionen von Visual C++ nicht unterstützt und MFC bereitgestellten Makros **TRY/CATCH/THROW** stattdessen verwendet wurden. C++-Ausnahmen werden von dieser Version von Visual C++ vollständig unterstützt. In diesem Hinweis behandelt einige der erweiterten Implementierungsdetails der vorherigen Makros auch automatisch basierenden Bereinigen von Objekten. Da C++-Ausnahmen stapelentladung standardmäßig unterstützt, ist diese technische Hinweis nicht mehr erforderlich.

Finden Sie unter [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) für Weitere Informationen zu den Unterschieden zwischen den MFC-Makros und die neuen C++-Schlüsselwörter.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

