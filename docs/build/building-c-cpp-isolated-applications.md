---
title: Erstellen isolierter C/C++-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: f550125c9e7dcbddcd992652dff7fd23824eeec8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413029"
---
# <a name="building-cc-isolated-applications"></a>Erstellen isolierter C/C++-Anwendungen

Eine isolierte Anwendung hängt nur von Seite-an-Seite-Assemblys und bindet an seine Abhängigkeiten mithilfe eines Manifests. Es ist nicht erforderlich, für die Anwendung vollständig isoliert, um ordnungsgemäß unter Windows ausgeführt werden. Sie können jedoch durch eine Investition in Ihre Anwendung isoliert, Zeit sparen, wenn Sie Ihre Anwendung in der Zukunft müssen. Weitere Informationen zu den Vorteilen der wird Ihre Anwendung isoliert, finden Sie unter [isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications).

Wenn Sie Ihre systemeigene C/C++-Anwendung mit Visual C++ erstellen, generiert Projektsystem standardmäßig der Visual Studio eine manifest-Datei, die die Abhängigkeiten Ihrer Anwendung von Visual C++-Bibliotheken zu beschreiben. Wenn dies die einzigen Abhängigkeiten sind verfügt Ihre Anwendung, wird er einer isolierten Anwendung angezeigt wird, sobald er mit Visual Studio neu erstellt wird. Wenn Ihre Anwendung zur Laufzeit andere Bibliotheken verwendet, müssen Sie möglicherweise diese Bibliotheken als Seite-an-Seite-Assemblys, die anhand der Schritte erneut [Erstellen von C/C++-Seite-an-Seite-Assemblys](../build/building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
