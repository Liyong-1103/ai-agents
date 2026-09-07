# W2｜Course Check

这是一个不影响未来课程项目的本节课实验。它只用来观察：一个 GitHub fork 中的简单改动，能否在另一台机器上随项目一起出现。

## 在自己的 fork 中留下公开签名

先在 GitHub 网页 fork 课程仓库，再把 [`signature.toml`](signature.toml) 中的教师默认值改为教师分配的公开课程代号：

```toml
[student]
signature = "s07"
```

不要写姓名、完整学号、密码、token 或其他个人信息。

## 在自己的机器上观察同学的 fork

与同学交换 fork 的 HTTPS URL，把对方仓库 clone 到一个新目录，然后进入：

```bash
cd warmups/week-02/course-check
uv sync --locked
COURSE_MODE=fixture uv run --locked python course_check.py
COURSE_MODE=fixture uv run --locked pytest -q
```

程序应当报告同学的公开课程代号，而不是：

```text
signature: teacher
```

测试通过只说明程序在当前项目环境中按给定规则运行。是否确实看到了同学的签名，仍需要运行者亲自判断。

本实验不提交回教师仓库，不构成 W3 或后续项目的代码基础。完成与否都不限制进入下一周。

