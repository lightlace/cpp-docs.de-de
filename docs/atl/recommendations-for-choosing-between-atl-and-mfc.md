---
title: Empfehlungen für die Wahl zwischen ATL und MFC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a9bbf30c728b6562da0c56c25b177697f0882a5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762124"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>Empfehlungen für die Wahl zwischen ATL und MFC

Wenn Sie Komponenten und Anwendungen zu entwickeln, können Sie zwischen zwei Ansätzen: ATL- und MFC (Microsoft Foundation Class-Bibliothek).

## <a name="using-atl"></a>Verwendung von ATL

ATL handelt es sich um eine schnelle und einfache Möglichkeit, eine COM-Komponente in C++ erstellen und verwalten einen kleinen Speicherbedarf. Verwenden Sie ATL ein Steuerelement erstellt, wenn Sie alle integrierten Funktionen nicht benötigen, die MFC automatisch bereitstellt.

## <a name="using-mfc"></a>Verwenden von MFC

MFC können Sie vollständige Anwendungen, ActiveX-Steuerelemente und aktive Dokumente zu erstellen. Wenn Sie bereits ein Steuerelements mit MFC erstellt haben, empfiehlt es sich um die Entwicklung in MFC fortzusetzen. Wenn Sie ein neues Steuerelement erstellen zu können, sollten Sie mit ATL, wenn Sie alle MFC integrierten Funktionen nicht benötigen.

## <a name="using-atl-in-an-mfc-project"></a>Verwenden ATL in einem MFC-Projekt

Sie können Unterstützung für die Verwendung von ATL in einem vorhandenen MFC-Projekt mithilfe ein Assistenten hinzufügen. Weitere Informationen finden Sie unter [ATL-Unterstützung hinzufügen, MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>Siehe auch

[Einführung in ATL](../atl/introduction-to-atl.md)

