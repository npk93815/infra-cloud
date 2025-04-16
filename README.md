# infra-cloud

# Part I - csvserver Setup

## Step-by-step commands:

1. Pull image:
```bash
docker pull infracloudio/csvserver:latest
./gencsv.sh 2 8
docker run -d --name csvserver -p 9393:9300 -e CSVSERVER_BORDER=Orange -v $(pwd)/inputFile:/csvserver/inputdata infracloudio/csvserver:latest
Verify output: Visit http://localhost:9393
curl -o ./part-1-output http://localhost:9393/raw
docker logs csvserver >& part-1-logs

---

### 🔹 Step 9: GitHub Commit

Make sure these files exist in your `solution` directory:
- `gencsv.sh`
- `inputFile`
- `part-1-cmd`
- `part-1-output`
- `part-1-logs`
- `README.md`

Then commit and push:

```bash
git init
git remote add origin https://github.com/YOUR-USERNAME/YOUR-PRIVATE-REPO.git
git add .
git commit -m "Part 1 complete - csvserver working"
git push -u origin main
