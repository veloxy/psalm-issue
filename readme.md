# Info

```
php -v
PHP 8.1.10 (cli) (built: Sep  3 2022 12:09:27) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.10, Copyright (c) Zend Technologies
    with Zend OPcache v8.1.10, Copyright (c), by Zend Technologies
    with Xdebug v3.1.4, Copyright (c) 2002-2022, by Derick Rethans
```

# Install vendors

`composer install`

# Run Psalm

`vendor/bin/psalm --no-cache --debug-by-line`

## Output

```
Analyzing files...
Getting /Users/kevin/Development/psalm-test/src/psalm.php
Analyzing /Users/kevin/Development/psalm-test/src/psalm.php
/Users/kevin/Development/psalm-test/src/psalm.php:3
/Users/kevin/Development/psalm-test/src/psalm.php:7
Uncaught InvalidArgumentException: Could not get class storage for static in /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Provider/ClassLikeStorageProvider.php:48
Stack trace:
#0 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Type.php(917): Psalm\Internal\Provider\ClassLikeStorageProvider->get('static')
#1 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Type.php(848): Psalm\Type::mayHaveIntersection(Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Codebase))
#2 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Type.php(704): Psalm\Type::intersectAtomicTypes(Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Codebase), false)
#3 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Codebase/Methods.php(807): Psalm\Type::intersectUnionTypes(Object(Psalm\Type\Union), Object(Psalm\Type\Union), Object(Psalm\Codebase))
#4 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/Expression/Call/Method/MethodCallReturnTypeFetcher.php(182): Psalm\Internal\Codebase\Methods->getMethodReturnType(Object(Psalm\Internal\MethodIdentifier), 'Symfony\\Compone...', Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Array)
#5 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/Expression/Call/Method/ExistingAtomicMethodCallAnalyzer.php(254): Psalm\Internal\Analyzer\Statements\Expression\Call\Method\MethodCallReturnTypeFetcher::fetch(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(Psalm\Codebase), Object(PhpParser\Node\Expr\MethodCall), Object(Psalm\Context), Object(Psalm\Internal\MethodIdentifier), Object(Psalm\Internal\MethodIdentifier), Object(Psalm\Internal\MethodIdentifier), 'Symfony\\Compone...', Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Type\Atomic\TNamedObject), Array, Object(Psalm\Internal\Analyzer\Statements\Expression\Call\Method\AtomicMethodCallAnalysisResult), Object(Psalm\Internal\Type\TemplateResult))
#6 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/Expression/Call/Method/AtomicMethodCallAnalyzer.php(470): Psalm\Internal\Analyzer\Statements\Expression\Call\Method\ExistingAtomicMethodCallAnalyzer::analyze(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Expr\MethodCall), Object(PhpParser\Node\Identifier), Array, Object(Psalm\Codebase), Object(Psalm\Context), Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Type\Atomic\TNamedObject), NULL, Object(Psalm\Internal\MethodIdentifier), Object(Psalm\Internal\Analyzer\Statements\Expression\Call\Method\AtomicMethodCallAnalysisResult), NULL)
#7 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/Expression/Call/MethodCallAnalyzer.php(188): Psalm\Internal\Analyzer\Statements\Expression\Call\Method\AtomicMethodCallAnalyzer::analyze(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Expr\MethodCall), Object(Psalm\Codebase), Object(Psalm\Context), Object(Psalm\Type\Union), Object(Psalm\Type\Atomic\TNamedObject), Object(Psalm\Type\Atomic\TNamedObject), false, NULL, Object(Psalm\Internal\Analyzer\Statements\Expression\Call\Method\AtomicMethodCallAnalysisResult), NULL)
#8 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/ExpressionAnalyzer.php(186): Psalm\Internal\Analyzer\Statements\Expression\Call\MethodCallAnalyzer::analyze(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Expr\MethodCall), Object(Psalm\Context), true, NULL)
#9 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/Statements/ExpressionAnalyzer.php(86): Psalm\Internal\Analyzer\Statements\ExpressionAnalyzer::handleExpression(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Expr\MethodCall), Object(Psalm\Context), false, NULL, true, NULL, false)
#10 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/StatementsAnalyzer.php(586): Psalm\Internal\Analyzer\Statements\ExpressionAnalyzer::analyze(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Expr\MethodCall), Object(Psalm\Context), false, NULL, true)
#11 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/StatementsAnalyzer.php(212): Psalm\Internal\Analyzer\StatementsAnalyzer::analyzeStatement(Object(Psalm\Internal\Analyzer\StatementsAnalyzer), Object(PhpParser\Node\Stmt\Expression), Object(Psalm\Context), NULL)
#12 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/FileAnalyzer.php(205): Psalm\Internal\Analyzer\StatementsAnalyzer->analyze(Array, Object(Psalm\Context), NULL, true)
#13 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Codebase/Analyzer.php(1600): Psalm\Internal\Analyzer\FileAnalyzer->analyze()
#14 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Codebase/Analyzer.php(539): Psalm\Internal\Codebase\Analyzer->analysisWorker(0, '/Users/kevin/De...')
#15 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Codebase/Analyzer.php(290): Psalm\Internal\Codebase\Analyzer->doAnalysis(Object(Psalm\Internal\Analyzer\ProjectAnalyzer), 9)
#16 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Analyzer/ProjectAnalyzer.php(708): Psalm\Internal\Codebase\Analyzer->analyzeFiles(Object(Psalm\Internal\Analyzer\ProjectAnalyzer), 9, false, true)
#17 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/src/Psalm/Internal/Cli/Psalm.php(376): Psalm\Internal\Analyzer\ProjectAnalyzer->check('/Users/kevin/De...', true)
#18 /Users/kevin/Development/psalm-test/vendor/vimeo/psalm/psalm(9): Psalm\Internal\Cli\Psalm::run(Array)
#19 {main}
(Psalm 5.0.0@4e177bf0c9f03c17d2fbfd83b7cc9c47605274d8 crashed due to an uncaught Throwable
```
