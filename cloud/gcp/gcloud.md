이곳은 GCP관련 기능을 정리하는 곳이다.
===

# 1. gcloud로 기본 사용법
    # 프로젝트가져오기
    gcloud projects list --sort-by=projectId

    # 프로젝트 선택
    gcloud config set project my-project-id

# 2. gcloud로 cluster 접속
    gcloud container clusters get-credentials my-cluster --zone=my-zone --project my-project-id

# 3. gcloud dns recod-set 빼는 법
    # 프로젝트가져오기
    gcloud projects list --sort-by=projectId

    # 프로젝트 선택
    gcloud config set project my-project-id

    # record sets list 보기
    gcloud dns record-sets list --zone my-zone

    #  record sets export 하기
    gcloud dns record-sets export my_file.yaml --zone=my-zone

    #  record set import 하기
    gcloud dns record-sets import my_file.yaml --zone-file-format --zone=my-zone