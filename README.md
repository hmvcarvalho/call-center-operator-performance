# Analyzing operator performance
*TripleTen Data Analyst bootcamp final project*

CallMeMaybe is a cloud telephony service used by companies that need to manage high volumes of calls.

The company is developing a new feature that will allow each client's supervisors to identify underperforming agents based on unanswered calls, waiting time on inbound calls and the number of calls made by outbound agents.

This project aims to identify underperforming agents and test statistical hypotheses about their performance. The results will give supervisors data to act on and to create action plans that improve overall performance.

## Data

The data was provided by TripleTen and represents the usage of the CallMeMaybe service. It is stored in the `data/` folder.

### `telecom_dataset_new.csv` — call statistics

Each row aggregates calls with the same characteristics (client, date, direction, internal/external, operator and missed status). The `calls_count` column indicates how many calls the row represents, so durations should be interpreted accordingly.

| Column | Description |
|---|---|
| `user_id` | Client account ID |
| `date` | Date the statistics were collected |
| `direction` | Call direction: `in` (inbound) or `out` (outbound) |
| `internal` | Whether the call was internal (between operators of the same client) |
| `operator_id` | Operator ID |
| `is_missed_call` | Whether the call was missed |
| `calls_count` | Number of calls |
| `call_duration` | Call duration, excluding waiting time |
| `total_call_duration` | Call duration, including waiting time |

### `telecom_clients.csv` — client information

| Column | Description |
|---|---|
| `user_id` | Client ID |
| `tariff_plan` | Client's current tariff plan |
| `date_start` | Client's registration date |

## Repository structure

```text
call-center-operator-performance/
├── data/
│   ├── telecom_clients.csv
│   └── telecom_dataset_new.csv
├── notebooks/
│   └── 01_task_decomposition.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

## Setup

### Prerequisites

- Python 3.12 or later
- Git

### Installation

1. Clone the repository:

```bash
git clone https://github.com/hmvcarvalho/call-center-operator-performance.git
cd call-center-operator-performance
```

2. Create a virtual environment:

```bash
python -m venv .venv
```

3. Activate it:

- Windows (PowerShell): `.venv\Scripts\Activate.ps1`
- Windows (CMD): `.venv\Scripts\activate`
- macOS/Linux: `source .venv/bin/activate`

4. Install the dependencies:

```bash
pip install -r requirements.txt
```

### Running the notebooks

Open the notebooks in the `notebooks/` folder with Jupyter or VS Code and select the `.venv` environment as the kernel. Run the cells in order, from top to bottom.