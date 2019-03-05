---
title: Empfehlungen für die Wahl zwischen ATL und MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: e4e51f81bbdc54ff09980acfba22037df77abac9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259775"
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
