---
title: 'CA1016: Assemblys mit AssemblyVersionAttribute markieren'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7fbc3fa747171892066705ddc32a114cb34e1b02
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47858174"
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: Assemblys mit AssemblyVersionAttribute markieren

|||
|-|-|
|TypeName|MarkAssembliesWithAssemblyVersion|
|CheckId|CA1016|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache

Die Assembly muss sich nicht auf eine Versionsnummer aus.

## <a name="rule-description"></a>Regelbeschreibung

Die Identität einer Assembly besteht aus den folgenden Informationen:

- Assemblyname

- Versionsnummer

- culture

- Öffentliche Schlüssel (für Assemblys mit starkem Namen).

.NET Framework verwendet die Versionsnummer, um eine Assembly eindeutig zu identifizieren, und klicken Sie zum Binden an Datentypen in Assemblys mit starkem Namen. Die Versionsnummer wird zusammen mit der Versions- und Herausgeberrichtlinie verwendet. Standardmäßig werden Anwendungen nur mit der Assemblyversion ausgeführt, mit der sie erstellt wurden.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, fügen Sie eine Versionsnummer der Assembly mithilfe der <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> Attribut. Weitere Informationen finden Sie im folgenden Beispiel.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Unterdrücken Sie eine Warnung dieser Regel nicht für Assemblys, die von Drittanbietern oder in einer produktionsumgebung verwendet werden.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt eine Assembly, die <xref:System.Reflection.AssemblyVersionAttribute> -Attribut.

 [!code-csharp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]

## <a name="see-also"></a>Siehe auch

- [Assemblyversionen](/dotnet/framework/app-domains/assembly-versioning)
- [Gewusst wie: Erstellen einer Herausgeberrichtlinie](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)