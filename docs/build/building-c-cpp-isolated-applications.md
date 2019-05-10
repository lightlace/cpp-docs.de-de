---
title: Erstellen isolierter C/C++-Anwendungen
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: 42192ad9388a8e69b70947c20c6fa7ee428a2bb9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220959"
---
# <a name="building-cc-isolated-applications"></a>Erstellen isolierter C/C++-Anwendungen

Eine isolierte Anwendung hängt nur von Seite-an-Seite-Assemblys und bindet an seine Abhängigkeiten mithilfe eines Manifests. Es ist nicht erforderlich, für die Anwendung vollständig isoliert, um ordnungsgemäß unter Windows ausgeführt werden. Sie können jedoch durch eine Investition in Ihre Anwendung isoliert, Zeit sparen, wenn Sie Ihre Anwendung in der Zukunft müssen. Weitere Informationen zu den Vorteilen der wird Ihre Anwendung isoliert, finden Sie unter [isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications).

Wenn Sie die Erstellung Ihrer systemeigenen C /C++ -Anwendung mit Visual Studio standardmäßig das Projektsystem von Visual Studio generiert eine Manifestdatei, die die Abhängigkeiten Ihrer Anwendung von Visual Studio-Bibliotheken zu beschreiben. Wenn dies die einzigen Abhängigkeiten sind verfügt Ihre Anwendung, wird er einer isolierten Anwendung angezeigt wird, sobald er mit Visual Studio neu erstellt wird. Wenn Ihre Anwendung zur Laufzeit andere Bibliotheken verwendet, müssen Sie möglicherweise diese Bibliotheken als Seite-an-Seite-Assemblys, die anhand der Schritte erneut [Erstellen von C/C++-Seite-an-Seite-Assemblys](building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
