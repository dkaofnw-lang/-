<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>StudyMate</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, "Noto Sans KR", sans-serif;
    background: #f6f8fc;
    color: #202633;
}

button {
    font-family: inherit;
}

header {
    height: 70px;
    background: white;
    border-bottom: 1px solid #e8ebf0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 7%;
    position: sticky;
    top: 0;
    z-index: 100;
}

.logo {
    font-size: 23px;
    font-weight: bold;
    color: #3678e8;
}

.logo span {
    color: #222;
}

nav {
    display: flex;
    gap: 5px;
}

nav button {
    border: none;
    background: transparent;
    padding: 10px 14px;
    border-radius: 8px;
    color: #667085;
    cursor: pointer;
    font-size: 14px;
}

nav button:hover,
nav button.active {
    color: #3678e8;
    background: #edf4ff;
}

main {
    max-width: 1100px;
    margin: auto;
    padding: 35px 20px 70px;
}

.page {
    display: none;
}

.page.active {
    display: block;
}

/* 공통 */

h1 {
    font-size: 28px;
    margin-bottom: 8px;
}

.subtitle {
    color: #737b8c;
    margin-bottom: 25px;
}

.card {
    background: white;
    border-radius: 18px;
    padding: 25px;
    margin-bottom: 20px;
    box-shadow: 0 5px 20px rgba(30, 50, 80, 0.05);
}

.btn {
    border: none;
    border-radius: 10px;
    padding: 12px 18px;
    cursor: pointer;
    font-weight: bold;
}

.primary {
    background: #3678e8;
    color: white;
}

.primary:hover {
    background: #2866d2;
}

.secondary {
    background: #eef2f7;
    color: #505969;
}

/* 홈 */

.hero {
    background: linear-gradient(135deg, #3678e8, #6a9cf4);
    color: white;
    border-radius: 22px;
    padding: 42px;
    margin-bottom: 22px;
}

.hero h1 {
    font-size: 31px;
    margin: 0 0 12px;
}

.hero p {
    line-height: 1.7;
    opacity: .92;
    margin: 0;
}

.stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    margin-bottom: 30px;
}

.stat {
    background: white;
    padding: 20px;
    border-radius: 15px;
    text-align: center;
}

.stat-number {
    color: #3678e8;
    font-size: 25px;
    font-weight: bold;
    margin-bottom: 5px;
}

.section-title {
    margin: 25px 0 15px;
}

.features {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
}

.feature {
    background: white;
    border-radius: 17px;
    padding: 23px;
    cursor: pointer;
    transition: .2s;
    border: 1px solid transparent;
}

.feature:hover {
    transform: translateY(-3px);
    border-color: #cbdcff;
}

.feature-icon {
    font-size: 29px;
    margin-bottom: 12px;
}

.feature h3 {
    margin: 0 0 8px;
}

.feature p {
    margin: 0;
    color: #737b8c;
    line-height: 1.6;
    font-size: 14px;
}

/* 좌석 */

.legend {
    display: flex;
    gap: 18px;
    margin-bottom: 20px;
    font-size: 13px;
    color: #626b7a;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 6px;
}

.legend-dot {
    width: 13px;
    height: 13px;
    border-radius: 4px;
}

.empty-dot {
    background: #dff5e5;
    border: 1px solid #65bd7a;
}

.used-dot {
    background: #ffe1e1;
    border: 1px solid #ed7777;
}

.my-dot {
    background: #dceaff;
    border: 1px solid #3678e8;
}

.room {
    background: #f0f3f7;
    border: 1px solid #dce1e9;
    border-radius: 15px;
    padding: 25px;
}

.window {
    background: #d8ecff;
    color: #4277a5;
    text-align: center;
    padding: 9px;
    border-radius: 8px;
    margin-bottom: 25px;
    font-size: 14px;
    font-weight: bold;
}

.seat-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 12px;
}

.seat {
    height: 78px;
    border-radius: 12px;
    border: 2px solid #65bd7a;
    background: #dff5e5;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    cursor: pointer;
    transition: .2s;
}

.seat:hover {
    transform: translateY(-2px);
}

.seat.used {
    background: #ffe1e1;
    border-color: #ed7777;
    cursor: pointer;
}

.seat.mine {
    background: #dceaff;
    border-color: #3678e8;
}

.seat-number {
    font-size: 17px;
    font-weight: bold;
}

.seat-status {
    margin-top: 5px;
    font-size: 11px;
}

.last-update {
    text-align: center;
    margin-top: 15px;
    font-size: 12px;
    color: #89919f;
}

/* 추천 */

.form-group {
    margin-bottom: 23px;
}

.form-group label {
    display: block;
    font-weight: bold;
    margin-bottom: 10px;
}

.options {
    display: flex;
    flex-wrap: wrap;
    gap: 9px;
}

.option {
    padding: 10px 15px;
    border-radius: 20px;
    border: 1px solid #d9dee7;
    background: white;
    cursor: pointer;
    font-size: 14px;
}

.option.selected {
    background: #e8f0ff;
    color: #3678e8;
    border-color: #3678e8;
    font-weight: bold;
}

.result {
    display: none;
    margin-top: 22px;
    padding: 20px;
    background: #f0f6ff;
    border: 1px solid #d3e2ff;
    border-radius: 12px;
}

.result strong {
    color: #3678e8;
}

/* 파트너 */

select {
    width: 100%;
    padding: 13px;
    border: 1px solid #d9dee7;
    border-radius: 9px;
    background: white;
    font-size: 14px;
}

.partner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 17px;
    border: 1px solid #e5e8ee;
    border-radius: 13px;
    margin-bottom: 12px;
}

.profile {
    display: flex;
    align-items: center;
    gap: 13px;
}

.profile-icon {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: #edf3ff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
}

.tags {
    margin-top: 6px;
}

.tag {
    display: inline-block;
    background: #f0f2f5;
    padding: 4px 7px;
    border-radius: 5px;
    font-size: 11px;
    color: #667085;
    margin-right: 4px;
}

.match {
    text-align: right;
    color: #3678e8;
    font-weight: bold;
}

/* 업데이트 */

.my-seat-box {
    background: #f7f9fc;
    border-radius: 12px;
    padding: 18px;
    margin-bottom: 20px;
}

.notice {
    background: #fff8e6;
    border: 1px solid #f2dfaa;
    padding: 14px;
    border-radius: 9px;
    font-size: 13px;
    color: #77652f;
    margin-top: 18px;
}

/* 모바일 */

@media(max-width: 700px) {

    header {
        height: auto;
        padding: 14px;
        flex-direction: column;
        gap: 10px;
    }

    nav {
        width: 100%;
        overflow-x: auto;
    }

    nav button {
        white-space: nowrap;
        font-size: 12px;
    }

    .hero {
        padding: 28px;
    }

    .hero h1 {
        font-size: 25px;
    }

    .stats,
    .features {
        grid-template-columns: 1fr;
    }

    .seat-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
</style>
</head>


<body>

<header>

    <div class="logo">
        Study<span>Mate</span>
    </div>

    <nav>
        <button class="nav active" onclick="showPage('home', this)">
            홈
        </button>

        <button class="nav" onclick="showPage('seats', this)">
            좌석
        </button>

        <button class="nav" onclick="showPage('recommend', this)">
            자리 추천
        </button>

        <button class="nav" onclick="showPage('partner', this)">
            공부 파트너
        </button>

        <button class="nav" onclick="showPage('update', this)">
            내 자리
        </button>
    </nav>

</header>


<main>

<!-- ================= 홈 ================= -->

<section id="home" class="page active">

    <div class="hero">
        <h1>나에게 맞는 공부 환경을 찾아보세요.</h1>

        <p>
            자습실 좌석을 확인하고 원하는 환경의 자리를 찾거나
            나와 잘 맞는 공부 파트너를 만나보세요.
        </p>
    </div>


    <div class="stats">

        <div class="stat">
            <div class="stat-number" id="emptyCount">0</div>
            <div>현재 확인된 빈자리</div>
        </div>

        <div class="stat">
            <div class="stat-number" id="usedCount">0</div>
            <div>사용 중인 자리</div>
        </div>

        <div class="stat">
            <div class="stat-number">12</div>
            <div>등록된 공부 파트너</div>
        </div>

    </div>


    <h2 class="section-title">StudyMate 주요 기능</h2>


    <div class="features">

        <div class="feature" onclick="showPage('seats')">

            <div class="feature-icon">🪑</div>

            <h3>자습실 좌석 확인</h3>

            <p>
                자습실의 좌석 배치도와 현재 확인된
                빈자리를 한눈에 확인할 수 있습니다.
            </p>

        </div>


        <div class="feature" onclick="showPage('recommend')">

            <div class="feature-icon">🔍</div>

            <h3>맞춤형 자리 추천</h3>

            <p>
                원하는 공부 환경을 선택하면
                조건에 맞는 자리를 추천합니다.
            </p>

        </div>


        <div class="feature" onclick="showPage('partner')">

            <div class="feature-icon">🤖</div>

            <h3>AI 공부 파트너</h3>

            <p>
                공부 과목과 시간, 공부 방식을 비교하여
                나와 비슷한 학생을 찾아줍니다.
            </p>

        </div>


        <div class="feature" onclick="showPage('update')">

            <div class="feature-icon">🔄</div>

            <h3>좌석 정보 업데이트</h3>

            <p>
                자신의 자리 정보를 직접 등록하여
                자습실 좌석 정보를 업데이트합니다.
            </p>

        </div>

    </div>

</section>



<!-- ================= 좌석 확인 ================= -->

<section id="seats" class="page">

    <h1>자습실 좌석</h1>

    <p class="subtitle">
        현재 확인된 자습실 좌석 상태입니다.
    </p>


    <div class="card">

        <div class="legend">

            <div class="legend-item">
                <div class="legend-dot empty-dot"></div>
                빈자리
            </div>

            <div class="legend-item">
                <div class="legend-dot used-dot"></div>
                사용 중
            </div>

            <div class="legend-item">
                <div class="legend-dot my-dot"></div>
                내 자리
            </div>

        </div>


        <div class="room">

            <div class="window">
                🪟 창문
            </div>

            <div class="seat-grid" id="seatGrid"></div>

        </div>


        <div class="last-update">
            좌석 정보는 학생들이 직접 업데이트한 정보를 기준으로 표시됩니다.
        </div>

    </div>

</section>



<!-- ================= 자리 추천 ================= -->

<section id="recommend" class="page">

    <h1>맞춤형 자리 추천</h1>

    <p class="subtitle">
        원하는 공부 환경을 선택해 주세요.
    </p>


    <div class="card">

        <div class="form-group">

            <label>원하는 위치</label>

            <div class="options">

                <div class="option" data-value="창가">
                    창가
                </div>

                <div class="option" data-value="가운데">
                    가운데
                </div>

                <div class="option" data-value="출입문과 먼 곳">
                    출입문과 먼 곳
                </div>

            </div>

        </div>


        <div class="form-group">

            <label>원하는 공부 환경</label>

            <div class="options">

                <div class="option" data-value="조용한 자리">
                    조용한 자리
                </div>

                <div class="option" data-value="콘센트 근처">
                    콘센트 근처
                </div>

                <div class="option" data-value="사람이 적은 자리">
                    사람이 적은 자리
                </div>

            </div>

        </div>


        <button class="btn primary" onclick="recommendSeat()">
            내 조건에 맞는 자리 찾기
        </button>


        <div class="result" id="recommendResult"></div>

    </div>

</section>



<!-- ================= 공부 파트너 ================= -->

<section id="partner" class="page">

    <h1>AI 공부 파트너</h1>

    <p class="subtitle">
        나와 비슷한 공부 조건을 가진 학생을 찾아보세요.
    </p>


    <div class="card">

        <div class="form-group">

            <label>주로 공부하는 과목</label>

            <select id="subject">

                <option value="math">수학</option>
                <option value="english">영어</option>
                <option value="science">과학</option>
                <option value="korean">국어</option>
                <option value="social">사회</option>

            </select>

        </div>


        <div class="form-group">

            <label>선호하는 공부 시간</label>

            <select id="studyTime">

                <option value="early">
                    오후 5시 ~ 7시
                </option>

                <option value="evening">
                    오후 7시 ~ 9시
                </option>

                <option value="late">
                    오후 9시 이후
                </option>

            </select>

        </div>


        <div class="form-group">

            <label>선호하는 공부 방식</label>

            <select id="studyStyle">

                <option value="quiet">
                    조용히 각자 공부하기
                </option>

                <option value="question">
                    서로 질문하며 공부하기
                </option>

                <option value="discussion">
                    문제를 함께 풀기
                </option>

            </select>

        </div>


        <button class="btn primary" onclick="findPartners()">
            공부 파트너 찾기
        </button>

    </div>


    <div class="card">

        <h2>추천 공부 파트너</h2>

        <p style="color:#737b8c;">
            입력한 조건을 기준으로 추천합니다.
        </p>

        <div id="partnerList"></div>

    </div>

</section>



<!-- ================= 내 자리 ================= -->

<section id="update" class="page">

    <h1>내 자리 관리</h1>

    <p class="subtitle">
        현재 사용하고 있는 좌석을 등록하거나 자리를 비울 수 있습니다.
    </p>


    <div class="card">

        <div class="my-seat-box">

            <h3>현재 사용할 자리</h3>

            <select id="mySeat">

                <option value="1">1번 자리</option>
                <option value="2">2번 자리</option>
                <option value="3">3번 자리</option>
                <option value="4">4번 자리</option>
                <option value="5">5번 자리</option>
                <option value="6">6번 자리</option>
                <option value="7">7번 자리</option>
                <option value="8">8번 자리</option>
                <option value="9">9번 자리</option>
                <option value="10">10번 자리</option>
                <option value="11">11번 자리</option>
                <option value="12">12번 자리</option>
                <option value="13">13번 자리</option>
                <option value="14">14번 자리</option>
                <option value="15">15번 자리</option>
                <option value="16">16번 자리</option>
                <option value="17">17번 자리</option>
                <option value="18">18번 자리</option>
                <option value="19">19번 자리</option>
                <option value="20">20번 자리</option>

            </select>

        </div>


        <button class="btn primary" onclick="useSeat()">
            이 자리를 사용 중으로 등록
        </button>

        <button class="btn secondary" onclick="leaveSeat()">
            자리 비우기
        </button>


        <div class="notice">
            💡 자리에서 일어날 때 '자리 비우기'를 눌러주면
            다른 학생들이 해당 자리를 확인할 수 있습니다.
        </div>

    </div>

</section>

</main>



<script>

/* ========================================
   페이지 이동
======================================== */

function showPage(pageId, clickedButton) {

    document.querySelectorAll(".page").forEach(page => {
        page.classList.remove("active");
    });

    document.getElementById(pageId).classList.add("active");


    document.querySelectorAll(".nav").forEach(button => {
        button.classList.remove("active");
    });


    if (clickedButton) {
        clickedButton.classList.add("active");
    }


    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}


/* ========================================
   좌석 데이터
======================================== */

let seats =
    JSON.parse(localStorage.getItem("studyMateSeats"));


if (!seats) {

    seats = {};

    for (let i = 1; i <= 20; i++) {

        seats[i] = {
            status: "empty",
            updated: new Date().toLocaleTimeString()
        };

    }

    /* 처음 실행했을 때의 예시 데이터 */

    seats[3].status = "used";
    seats[7].status = "used";
    seats[13].status = "used";
    seats[18].status = "used";

    saveSeats();
}


function saveSeats() {

    localStorage.setItem(
        "studyMateSeats",
        JSON.stringify(seats)
    );

}


/* ========================================
   좌석 화면
======================================== */

function renderSeats() {

    const grid =
        document.getElementById("seatGrid");

    grid.innerHTML = "";


    let empty = 0;
    let used = 0;


    for (let i = 1; i <= 20; i++) {

        const seat =
            document.createElement("div");

        seat.className = "seat";


        if (seats[i].status === "used") {

            seat.classList.add("used");
            used++;

        } else {

            empty++;

        }


        seat.innerHTML = `

            <div class="seat-number">
                ${i}번
            </div>

            <div class="seat-status">
                ${
                    seats[i].status === "used"
                    ? "사용 중"
                    : "빈자리"
                }
            </div>

        `;


        seat.onclick = function() {

            if (seats[i].status === "empty") {

                if (
                    confirm(
                        `${i}번 자리를 사용 중으로 등록할까요?`
                    )
                ) {

                    seats[i].status = "used";

                    seats[i].updated =
                        new Date().toLocaleTimeString();

                    saveSeats();

                    renderSeats();
                }

            } else {

                alert(
                    `${i}번 자리는 현재 사용 중입니다.\n\n` +
                    `마지막 확인 시간: ${seats[i].updated}`
                );

            }

        };


        grid.appendChild(seat);

    }


    document.getElementById("emptyCount").innerText =
        empty;

    document.getElementById("usedCount").innerText =
        used;

}


/* ========================================
   좌석 업데이트
======================================== */

function useSeat() {

    const number =
        document.getElementById("mySeat").value;


    seats[number].status = "used";

    seats[number].updated =
        new Date().toLocaleTimeString();


    saveSeats();

    renderSeats();


    alert(
        `${number}번 자리가 사용 중으로 등록되었습니다.`
    );

}


function leaveSeat() {

    const number =
        document.getElementById("mySeat").value;


    seats[number].status = "empty";

    seats[number].updated =
        new Date().toLocaleTimeString();


    saveSeats();

    renderSeats();


    alert(
        `${number}번 자리가 빈자리로 변경되었습니다.`
    );

}


/* ========================================
   자리 조건 선택
======================================== */

document.querySelectorAll(".option").forEach(option => {

    option.addEventListener("click", function() {

        this.classList.toggle("selected");

    });

});


/* ========================================
   맞춤형 자리 추천
======================================== */

function recommendSeat() {

    const selected =
        [...document.querySelectorAll(".option.selected")]
        .map(option => option.dataset.value);


    const available =
        Object.keys(seats).filter(
            number =>
                seats[number].status === "empty"
        );


    const result =
        document.getElementById("recommendResult");


    if (available.length === 0) {

        result.innerHTML = `
            <strong>현재 확인된 빈자리가 없습니다.</strong>
            <br><br>
            좌석 정보가 업데이트되면 다시 확인해 주세요.
        `;

    } else {

        const recommended =
            available[
                Math.floor(
                    Math.random() * available.length
                )
            ];


        const condition =
            selected.length > 0
            ? selected.join(", ")
            : "특별한 조건 없음";


        result.innerHTML = `

            <strong>✨ 추천 결과</strong>

            <br><br>

            선택한 조건:
            <strong>${condition}</strong>

            <br><br>

            현재 확인된 빈자리 중
            <strong>${recommended}번 자리</strong>를 추천합니다.

            <br><br>

            <small>
                ※ 실제 서비스에서는 좌석별 위치,
                소음 정도, 콘센트 등의 정보를 바탕으로
                더욱 정확하게 추천할 수 있습니다.
            </small>

        `;

    }


    result.style.display = "block";

}


/* ========================================
   공부 파트너 데이터
======================================== */

const students = [

    {
        name: "김민준",
        subject: "math",
        time: "evening",
        style: "quiet",
        tags: ["수학", "저녁", "조용한 공부"]
    },

    {
        name: "이서윤",
        subject: "english",
        time: "evening",
        style: "question",
        tags: ["영어", "저녁", "질문하며 공부"]
    },

    {
        name: "박지훈",
        subject: "math",
        time: "early",
        style: "question",
        tags: ["수학", "오후", "질문하며 공부"]
    },

    {
        name: "최유진",
        subject: "science",
        time: "late",
        style: "quiet",
        tags: ["과학", "늦은 시간", "조용한 공부"]
    },

    {
        name: "정하은",
        subject: "math",
        time: "evening",
        style: "discussion",
        tags: ["수학", "저녁", "문제 함께 풀기"]
    }

];


/* ========================================
   공부 파트너 찾기
======================================== */

function findPartners() {

    const subject =
        document.getElementById("subject").value;

    const time =
        document.getElementById("studyTime").value;

    const style =
        document.getElementById("studyStyle").value;


    const results =
        students.map(student => {

            let score = 0;


            if (student.subject === subject) {
                score += 40;
            }


            if (student.time === time) {
                score += 30;
            }


            if (student.style === style) {
                score += 30;
            }


            return {
                ...student,
                score: score
            };

        });


    results.sort(
        (a, b) => b.score - a.score
    );


    const list =
        document.getElementById("partnerList");


    list.innerHTML = "";


    results.slice(0, 3).forEach(student => {

        const item =
            document.createElement("div");

        item.className = "partner";


        item.innerHTML = `

            <div class="profile">

                <div class="profile-icon">
                    👤
                </div>

                <div>

                    <strong>
                        ${student.name}
                    </strong>

                    <div class="tags">

                        ${student.tags.map(tag =>
                            `<span class="tag">${tag}</span>`
                        ).join("")}

                    </div>

                </div>

            </div>


            <div class="match">

                ${student.score}%

                <br>

                <small>
                    조건 일치율
                </small>

            </div>

        `;


        list.appendChild(item);

    });

}


/* ========================================
   처음 실행
======================================== */

renderSeats();

</script>

</body>
</html>
