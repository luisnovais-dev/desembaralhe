# Arquitetura

## Plataforma e escopo

- MVP por dispositivo: o aplicativo roda no aparelho, com o diário local (ver especificação, seção Arquitetura do MVP).
- Plataforma inicial: **Android**, com iOS depois (ver [ADR 0001](adr/0001-plataforma-inicial-android.md)).

## Backend e chave de IA

Decidido na [ADR 0003](adr/0003-backend-chave-de-ia.md): um servidor guarda a chave de IA e a base editorial privada, monta o contexto e chama a IA. O diário fica no aparelho no piloto.

## Referência Android: dependências do Mobile-Harness

Origem: `luisnovais-dev/Mobile-Harness` (público), arquivos `settings.gradle.kts`, `build.gradle.kts`, `app/build.gradle.kts` e `gradle.properties`, lidos em 2026-11-25. O `gradle/libs.versions.toml` não existe nesse projeto: as versões ficam inline.

| Item | Versão de referência | Uso |
|---|---|---|
| Android Gradle Plugin | 8.13.2 | plugin de app |
| Kotlin / plugin Compose | 2.2.21 | linguagem e Compose |
| compileSdk / targetSdk | 36 (alvo do build Play) | |
| minSdk | 28 | |
| JVM | 17 | `compileOptions` e `jvmTarget` |
| compose-bom | 2025.02.00 | ui, material3, material-icons-extended, ui-tooling-preview |
| core-ktx | 1.15.0 | |
| activity-compose | 1.10.0 | |
| lifecycle (runtime, viewmodel) | 2.8.7 | |
| kotlinx-coroutines-android | 1.9.0 | |
| commons-compress | 1.27.1 | adotar só se o MVP descompactar arquivos |
| zstd-jni (aar) | 1.5.7-12 | adotar só se houver compressão zstd |
| junit | 4.13.2 (teste) | |
| org.json | 20250107 (teste) | |
| ui-tooling, ui-test-manifest | via BOM (debug) | |

Opções de `gradle.properties` a copiar: `android.useAndroidX=true`, `kotlin.code.style=official`, `android.nonTransitiveRClass=true`, `org.gradle.jvmargs=-Xmx3g -Dfile.encoding=UTF-8`.

**Não copiar** do Mobile-Harness, porque são do produto dele: PRoot e `third_party/` (submódulos), bundles de runtime em `dist/`, `externalNativeBuild`/CMake, NDK 28, sinalização de upload, a chave de teste do OpenRouter em `BuildConfig`, os flavors `online`/`offline` e o overlay de manifesto de Play e sideload.

## Referência não consultada: luisnovais-dev/tirzepatida-controle

Não está acessível a esta sessão (repositório privado, sem acesso concedido ao Claude). As dependências deste projeto ainda não foram comparadas com ele. Para liberar: instalar o GitHub App do Claude na organização ou no repositório, e então anexar o repositório.

## Pendências técnicas

- Lockfile: a definir (Gradle wrapper e `gradle/libs.versions.toml` são candidatos).
- Testes de UI e E2E: a definir.
- Armazenamento local do diário: a definir.
