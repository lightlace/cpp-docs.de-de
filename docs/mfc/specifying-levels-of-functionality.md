---
title: Festlegen von Funktionalitätsebenen
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: c3b4ecb38054748f36d75ca43e32d6447d3d2428
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299909"
---
# <a name="specifying-levels-of-functionality"></a>Festlegen von Funktionalitätsebenen

In diesem Artikel wird beschrieben, wie Sie die folgenden Ebenen der Funktionalität zum Hinzufügen Ihrer [CObject](../mfc/reference/cobject-class.md)-Klasse:

- Laufzeit Klasseninformationen

- Unterstützung für dynamische Erstellung

- Unterstützung von Serialisierung

Eine allgemeine Beschreibung von `CObject` Funktionen finden Sie im Artikel [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md).

## <a name="to-add-run-time-class-information"></a>Hinzufügen von Laufzeit Klasseninformationen

1. Leiten Sie eine Klasse von `CObject`gemäß der Beschreibung in der [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md) Artikel.

1. Verwenden Sie das DECLARE_DYNAMIC-Makro in der Klassendeklaration, wie hier gezeigt:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. Verwenden Sie das IMPLEMENT_DYNAMIC-Makro in der Implementierungsdatei (. CPP) der Klasse. Dieses Makro akzeptiert als Argumente den Namen der Klasse und ihrer Basisklasse wie folgt:

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> In der Implementierungsdatei IMPLEMENT_DYNAMIC einfach (. CPP) für die Klasse. Das IMPLEMENT_DYNAMIC-Makro nur einmal während einer Kompilierung ausgewertet werden soll, und sollte daher nicht in einer Schnittstellendatei verwendet werden (. H), kann möglicherweise in mehrere Dateien enthalten sein.

## <a name="to-add-dynamic-creation-support"></a>Hinzufügen von Unterstützung für dynamische Erstellung

1. Leiten Sie eine Klasse von `CObject`.

1. Verwenden Sie das DECLARE_DYNCREATE-Makro in der Klassendeklaration.

1. Definieren Sie einen Konstruktor ohne Argumente (eine Standardkonstruktor).

1. Verwenden Sie das IMPLEMENT_DYNCREATE-Makro in der Implementierungsdatei der Klasse.

## <a name="to-add-serialization-support"></a>Die Serialisierungsunterstützung hinzufügen

1. Leiten Sie eine Klasse von `CObject`.

1. Überschreiben der `Serialize` Member-Funktion.

   > [!NOTE]
   > Wenn Sie aufrufen `Serialize` direkt, d. h. Sie nicht möchten das Objekt über einen Zeiger polymorph zu serialisieren, überspringen Sie die Schritte 3 bis 5.

1. Verwenden Sie das DECLARE_SERIAL-Makro in der Klassendeklaration.

1. Definieren Sie einen Konstruktor ohne Argumente (eine Standardkonstruktor).

1. Verwenden Sie das IMPLEMENT_SERIAL-Makro in der Implementierungsdatei der Klasse.

> [!NOTE]
> "Polymorpher Zeiger" verweist auf ein Objekt einer Klasse (rufen Sie ihn ein) oder auf ein Objekt einer Klasse ein (z. B. B) abgeleitet. Um über einen Zeiger polymorph zu serialisieren, muss das Framework die Run-Time-Klasse des Objekts festlegen, es (B) serialisiert, da es ein Objekt einer Klasse, die von einer Basisklasse (A) abgeleitet werden kann.

Weitere Informationen zum Aktivieren der Serialisierung, wenn Sie eine Klasse von ableiten `CObject`, finden Sie in den Artikeln [Dateien in MFC](../mfc/files-in-mfc.md) und [Serialisierung](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md)
