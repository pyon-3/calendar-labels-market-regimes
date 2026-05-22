# Publishing Notes

## GitHub initialization

Replace `YOUR_HANDLE` with the actual GitHub handle.

```bash
mkdir calendar-labels-market-regimes
cd calendar-labels-market-regimes

mkdir -p paper results figures

touch README.md
touch paper/calendar_labels_market_instability_regimes_v0_1.md
touch figures/README.md
touch LICENSE
touch CITATION.cff
touch .gitignore

git init
git config user.name "pyon"
git config user.email "PUBLIC_EMAIL_OR_GITHUB_NOREPLY_EMAIL"
git add .
git commit -m "Initial research note v0.1"
git branch -M main
git remote add origin git@github.com:YOUR_HANDLE/calendar-labels-market-regimes.git
git push -u origin main
```

## Anonymous publishing checklist

- Confirm no real name is included.
- Confirm no affiliation name is included.
- Confirm no email address is included unless it is a public or GitHub noreply email.
- Confirm no local PC username or local absolute path is included.
- Confirm CSV and Markdown files contain no personal information.
- If a PDF is added later, inspect its author and creator metadata before release.
- Use repository-local Git config:

```bash
git config user.name "pyon"
git config user.email "PUBLIC_EMAIL_OR_GITHUB_NOREPLY_EMAIL"
```

## Twitter teaser

```text
水星逆行を「相場予測シグナル」ではなく、カレンダーラベルとして再検証しました。

結果、水星逆行単独のAUCは0.531と弱く、説明力の本体はVIX・MOVE・金利・ドルなどで構成した市場不安定レジーム側にありました。

星が相場を動かすのではなく、人間がショック後に星へ意味を貼る。

GitHub research note v0.1:
calendar-labels-market-regimes
```
