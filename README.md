# ocean-ochi-skill-cli

CLI สำหรับติดตั้ง **Oracle skills** + **company skills** ลง Claude Code (และ AI coding agents อื่น)
เป็น wrapper ครอบ [`arra-oracle-skills`](https://www.npmjs.com/package/arra-oracle-skills) (MIT, Soul-Brews-Studio) แล้วเสริม company skills จาก `src/skills/`

> ⚠️ **ต้องใช้ [Bun](https://bun.sh)** — bin เป็น TypeScript + shebang `#!/usr/bin/env bun` เรียกผ่าน `bunx --bun` ไม่ใช่ `npx`

## Install / Run

```bash
# รันตรงจาก registry (ไม่ต้องติดตั้งถาวร)
bunx --bun ocean-ochi-skill-cli install -p lab -y

# หรือ clone มารันจาก source
git clone https://github.com/firstnext/ocean-ochi-skill-cli.git
cd ocean-ochi-skill-cli
bun install
bun run src/cli/index.ts install -p lab -y
```

คำสั่งด้านบนเทียบเท่ากับ:

```bash
arra-oracle-skills@26.5.16 install -g --profile lab --agent claude-code -y
```

## `install` options

| Option | Default | คำอธิบาย |
|---|---|---|
| `-p, --profile <name>` | `standard` | Oracle skill profile: `minimal` / `standard` / `full` / `lab` |
| `--agent <name>` | `claude-code` | Target agent: `claude-code` / `cursor` / `opencode` / ... |
| `--oracle-version <ver>` | `26.5.16` | เวอร์ชัน `arra-oracle-skills` (เว้นว่าง = latest) |
| `-y, --yes` | — | ข้าม confirmation prompt |
| `--oracle-only` | — | ติดตั้ง Oracle skills อย่างเดียว |
| `--ochi-only` | — | ติดตั้ง company skills อย่างเดียว |

## Company skills

วาง skill ของบริษัทไว้ที่ `src/skills/<skill-name>/` — ตอน `install` จะถูก copy ไป `~/.claude/skills/`

## License

MIT
