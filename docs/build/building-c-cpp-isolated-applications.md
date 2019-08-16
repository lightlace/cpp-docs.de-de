---
title: Erstellen isolierter C/C++-Anwendungen
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: fbb553e3514ac3c32ee1e1f276dcb3e43d3a192e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493341"
---
# <a name="building-cc-isolated-applications"></a>Erstellen isolierter C/C++-Anwendungen

Eine isolierte Anwendung ist nur von parallelen Assemblys abhängig und bindet Sie mithilfe eines Manifests an ihre Abhängigkeiten. Es ist nicht erforderlich, dass Ihre Anwendung vollständig isoliert ist, damit Sie unter Windows ordnungsgemäß ausgeführt werden kann. Wenn Sie jedoch investieren, um Ihre Anwendung vollständig isoliert zu gestalten, können Sie Zeit sparen, wenn Sie Ihre Anwendung in Zukunft bedienen müssen. Weitere Informationen zu den Vorteilen der vollständigen Isolation Ihrer Anwendung finden Sie unter [isolierte Anwendungen](/windows/win32/SbsCs/isolated-applications).

Wenn Sie Ihre systemeigene C/C++ Anwendung mithilfe von Visual Studio erstellen, generiert das Visual Studio-Projekt System standardmäßig eine Manifest-Datei, die die Abhängigkeiten Ihrer Anwendung in Visual Studio-Bibliotheken beschreibt. Wenn dies die einzigen Abhängigkeiten der Anwendung ist, wird Sie zu einer isolierten Anwendung, sobald Sie mit Visual Studio neu erstellt wird. Wenn Ihre Anwendung andere Bibliotheken zur Laufzeit verwendet, müssen Sie diese Bibliotheken möglicherweise als parallele Assemblys neu erstellen, indem Sie die Schritte unter [Erstellen von C/C++ Seite-an-Seite-](building-c-cpp-side-by-side-assemblies.md)Assemblys befolgen.

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
